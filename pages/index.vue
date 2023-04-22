<template>
    <div>
        <div class="logo-container">
            <img class="logo" src="../assets/LakbayLogo.png" alt="Lakbay Logo">
        </div>
        <h1 class = "login-header">Welcome to Lakbay!</h1>
        <h2 class = "tagline">"Unveiling the hidden narratives of the world with Lakbay"</h2>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. In cum iure neque, sapiente vel laboriosam, voluptatum laudantium quia libero mollitia adipisci labore nulla sint harum necessitatibus totam corporis impedit quos incidunt veniam blanditiis obcaecati sunt, error quibusdam. Inventore dolorum voluptatibus voluptatum tempore sapiente error eligendi saepe odio voluptate, ratione autem?</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Explicabo magnam quisquam maxime repellendus voluptatum error tempore voluptates esse a eligendi?</p>
    </div>
</template>

<script setup>

</script>

<style scoped>
    .tagline {
        margin-bottom: 20px;
        font-size: 36 px;
        text-align: center;
        font-style: italic;
    }
    p {
        margin: 20px 0;
        margin-left: 200px;
        margin-right: 200px;
        text-align: center;

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
    .login-header{
        font-weight: 600;
        font-size: 25px;
        margin-bottom: 30px;
        line-height: 1.5;
        color: #000000;
        text-align: center;
    }
</style>