<template>
    <div>
        <div class="logo-container">
            <img class="logo" src="../assets/LakbayLogo.png" alt="Lakbay Logo">
        </div>
        <div class = login-container>
            <h1 class = "login-header">Welcome back to Lakbay!</h1>
            <h1 class = "login-styles">Email</h1>
            <input class = "login-input" v-model = "LoginInfo.useremail" type = "email" placeholder = "Enter Email"/>
            <h1 class = "login-styles">Password</h1>
            <input class = "login-input" v-model = "LoginInfo.userpassword" type = "password" placeholder = "Enter Password"/>
            <ul class = "signup-styles-register">
            <h1 class = "warning">{{ Warning }}</h1>
            
            <button v-on:click = "login" class = "btnregister">Login</button>
            </ul>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import Cookies from 'js-cookie'

  export default {
    data() {
      return {
        LoginInfo: {
          useremail: "",
          userpassword: ""
        },
        userToken: " ",
        Warning: "",
        authToken: ""
      };
    },
    methods: {
        login(){
            console.log(this.LoginInfo)
            if(this.LoginInfo.useremail && this.LoginInfo.userpassword){
                this.Warning = "",
                axios.post(`http://localhost:7000/loginpage/u/login`, this.LoginInfo)
                .then((response) => {
                    this.Warning = response.data.message;
                    const userToken = response.data.token;
                    Cookies.set('auth_token', userToken);
                    this.authToken = Cookies.get('auth_token')
                    console.log(this.authToken)
                    if(response.status==200){
                        localStorage.setItem("usertoken", JSON.stringify(response.data.token))
                        console.log("routing to homedashboard")
                        this.$router.push({name: 'home'})
                    }
                    
                })
                .catch(error => {
                    if (error.response) {
                    console.log(error.response.data.message); // this will log "Invalid email or password."
                    this.Warning = error.response.data.message;
                    } else {
                    console.log(error.message);
                    }
                });
                
            }
            else{
                this.Warning = "Check your inputs",
                console.log("no input")
            }
    },
    }
    };

</script>

<style scoped>
    .logo-container {
        max-width: 100%;
        text-align: center;
        }
    .logo {
        display: block; /* to allow horizontal margin auto to work */
        width: 25%;
        margin: 0 auto 30px; /* sets top and bottom margin to 0, left and right margin to auto */
        }
    .login-container {

        display: flex;
        flex-direction: column;
        text-align: center;
    }
    .login-header{
        font-weight: 600;
        font-size: 25px;
        margin-bottom: 30px;
        line-height: 1.5;
        color: #000000;
        text-align: center;
    }
    .login-styles{
        margin-left: 35%;
        margin-right: 35%;
        margin-bottom: 10px;
        text-align: left;
        font-weight: 400;
        font-size: 17px;
        line-height: 0.5;
        color: #000000;
    }
    .login-input{
        width: 30%;
        height: 40px;
        padding-left: 20px;
        display: block;
        margin-bottom: 20px;
        margin-right: auto;
        margin-left: auto;
        color: #ffffff;
        background-color: #3C3C3C;
    }
    .signup-styles-register{
        margin-top: 50px;
        margin-left: 35%;
        margin-right: 35%;
        margin-bottom: 50px;
        text-align: center;
        font-size: 20px;
        }
    .warning{
            margin-bottom: 30px;
            text-align: center;
            font-weight: 400;
            font-size: 15px;
            line-height: 1.5;
            color:red
        }
</style>