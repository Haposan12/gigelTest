<template>
  <div>
    <div class="box-shadow bg-white p-4">
      <h3>Profil user</h3>
      <div class="row">
        <div class="col">
          Nama
        </div>
        <div class="col">
          : {{profile.name}}
        </div>
      </div>
      <div class="row">
        <div class="col">
          Email
        </div>
        <div class="col">
          : {{profile.email}}
        </div>
      </div>
      <div class="row">
        <div class="col">
          Nomor Handphone
        </div>
        <div class="col">
          : {{profile.phone_number}}
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Sidebar from './../components/Sidebar'
import AuthService from './../service/AuthService'
export default {
  components: {
    'sidebar-menu':Sidebar
  },
  data () {
    return {
      profile: {}
    }
  },
  async created() {
    await AuthService.profile().then(res => {
      if(res.status) {
        this.profile = res.data
      }
    })
  },
}
</script>