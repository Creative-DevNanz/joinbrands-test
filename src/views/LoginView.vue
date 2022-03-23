<template>
  <div class="about">
    <h1>This is a Login page</h1>
    <div>
        <h5>E-mail</h5>
        <input type="email" v-model="email">
    </div>
    <div>
        <h5>Password</h5>
        <input type="password" v-model="password">
    </div>
    <div>
        <h5></h5>
        <button type="button" @click="login()">
            Login
        </button>
    </div>
  </div>
</template>

<script lang="ts">

export default {
    el: '...',
    email: '',
    password: '',
    
    methods: {
        login() {
            console.log("login button is clicked with email and password!", this.email, this.password);
            console.log("local storage value", localStorage)            
            if(this.email == localStorage.getItem('email') && this.password == localStorage.getItem("password"))
            {
                localStorage.setItem('success_login', 'success');
                window.location.href = '/profile';
            }                
            else {
                alert ('invalid user');
            }
        }
    }
}
</script>
