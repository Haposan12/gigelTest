### Clone
clone repository `git clone https://github.com/Haposan12/gigelTest.git`

### Install and Prepare
Please run `composer install` and `npm install`

### Copy .env file 
Run `cp .env.example .env` for Linux/Mac user

Run `copy .env.example .env` for Windows user

Then setting Database in MySQL as usual 

### Running
Run `php artisan migrate`& `php artisan passport:install`

Run `php artisan serve` & `npm run watch`

#### Register
Calon user wajib mengisi semua form yang disediakan.

#### Login
User wajib mengisi semua form yang disediakan untuk bisa masuk ke dalam dashboard.

#### Dashboard
Berisi informasi dari user (nama, email, nomor hp).

#### Update Profil User
Fitur untuk mengubah nama, email, dan nomor hp dari user. 

#### Ubah Password
Fitur untuk mengubah password. Sebelum mengubah password, user harus menginput password lama.

#### Note
- Password harus diawali dengan huruf besar. Contoh: Haposan123
