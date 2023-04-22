<template>
    <div>
        <div class="logo-container">
            <img class="logo" src="../assets/LakbayLogo.png" alt="Lakbay Logo">
        </div>

        <div>
            <h1 class = "signup-header">Sign up to Lakbay</h1>

            <h1 class = "signup-styles">First Name</h1>
            <input class = "signup-input" type = "text" placeholder = "Saul"/>

            <h1 class = "signup-styles">Last Name</h1>
            <input class = "signup-input"  type = "text" placeholder = "Goodman"/>

            <h1 class = "signup-styles">Date of Birth</h1>
            <input class="signup-input" type="date" value="2023-04-20">

            <h1 class = "signup-styles">City</h1>
            <input class = "signup-input"  type = "text" placeholder = "Albuquerque"/>

            <h1 class = "signup-styles">Email</h1>
            <input class = "signup-input"  type = "email" placeholder = "Saulgoodman@gmail.com"/>

            <h1 class = "signup-styles">Password</h1>
            <input class = "signup-input"  type = "password" placeholder = "Enter Password"/>

            <h1 class = "signup-styles">Confirm Password</h1>
            <input class = "signup-input" type = "password" placeholder = "Enter Password"/>

            <label class = "signup-styles">
                <input type ="checkbox" > Terms and Conditions
            </label>

            <ul class = "signup-styles-register">

                    <li><NuxtLink to = "/Home" class = "btnregister">Register</NuxtLink></li>
                </ul>

        </div>

    </div>
</template>

<script setup>

</script>

<style scoped>
    .flex{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .logo-container {
        max-width: 100%;
        text-align: center;
        }
    .logo {
        display: block; /* to allow horizontal margin auto to work */
        width: 25%;
        margin: 0 auto 30px; /* sets top and bottom margin to 0, left and right margin to auto */
        }
    
    .signup-container {
        border: 1px dashed gray;
        display: flex;
        flex-direction: column;
        text-align: center;
        }

    .signup-header{
        font-weight: 600;
        font-size: 25px;
        margin-bottom: 30px;
        line-height: 1.5;
        color: #000000;
        text-align: center;
        }

    .signup-styles{
        margin-left: 35%;
        margin-right: 35%;
        margin-bottom: 10px;
        text-align: left;
        font-weight: 400;
        font-size: 17px;
        line-height: 0.5;
        color: #000000;
        }

    .signup-input{
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

    .signup-input[type="date"] {
        text-align: left;
        font-size: 15px;
        color: #ffffff;
        }

    .signup-styles-register{
        margin-top: 50px;
        margin-left: 35%;
        margin-right: 35%;
        margin-bottom: 50px;
        text-align: center;
        font-size: 20px;
        }

</style>