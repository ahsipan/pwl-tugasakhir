<template>
    <form @submit.prevent="handleSubmit">
        <h3>Sign Up</h3>
        <div class="form-group">
            <label>Username</label>
            <input type="text" class="form-control" v-model="username" placeholder="Username"/>
        </div>
        <div class="form-group">
            <label>Email</label>
            <input type="email" class="form-control" v-model="email" placeholder="Email"/>
        </div>
        <div class="form-group">
            <label>Password</label>
            <input type="password" class="form-control" v-model="password" placeholder="Password"/>
        </div>
        <button class="btn btn-primary btn-block">Sign Up</button>
    </form>
</template>

<script>
import axios from 'axios'
    export default{
        name: 'Register',
        data(){
            return {
                username: '',
                email: '',
                password: '',
            }
        },
        methods: {
            async handleSubmit(){
                await axios.post('register', {
                    username : this.username,
                    email : this.email,
                    password : this.password
                });
                this.$router.push('/login');
            }
        }
    }
</script>