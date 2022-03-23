<template>
  <div class="about">
    <h1>This is a Signup page</h1>
    <div>
        <h5>User name</h5>
        <input type="text" v-model="username">
    </div>
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
        <button type="button" @click="signup()">
            Signup
        </button>
    </div>
  </div>
</template>

<script lang="ts">

export default {
    el: '...',
    username: '',
    email: '',
    password: '',
    
    methods: {
        signup() {
            localStorage.setItem('username', this.username);
            localStorage.setItem('email', this.email);
            localStorage.setItem('password', this.password);
            console.log('localStorage value', localStorage);
            window.location.href = '/login';
        }
    }
}
</script>
