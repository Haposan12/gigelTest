<template>
  <div>
  <div class="container h-100 mt-5">
    <div class="row h-100 justify-content-center align-items-center">
      <form class="col-5 box-shadow bg-white p-4" @submit.prevent="doLogin()">
        <h3 class="text-center mb-2">Login</h3>
        <div class="form-group">
          <input type="text" class="form-control" v-model="form.payload.email" placeholder="email">
        </div>
        <div class="form-group">
          <input type="password" class="form-control" v-model="form.payload.password" placeholder="password">
        </div>
        <div class="form-group">
          <button class="btn btn-primary btn-block">Login</button>
        </div>
        <p>
          <span>Belum memiliki akun?</span> <router-link :to="{name: 'Register'}">Register</router-link>
        </p>
      </form>   
    </div>
  </div>
  </div>
</template>
<script>
import AuthService from './../service/AuthService'
import {setLogin, setUser} from './../utils/Auth'
export default {
  data () {
    return {
      form: {
        payload: {
          email: '',
          password: ''
        }
      }
    }
  },
  methods: {
    async doLogin () {
      await AuthService.login(this.form).then(res => {
        const {status} = res
        if(!status) {
          return false;
        }
        console.log(res)
        setLogin(res.token)
        setUser(JSON.stringify(res.user))
        window.location.href = '/'
      })      
    }
  }
}
</script>