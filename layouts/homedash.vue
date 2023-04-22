<template>
    <div>
        <header class = "shadow-sm bg bg-mine-shaft-800">
            <nav class = "container mx-auto p-4 flex justify-between">
                <NuxtLink to = "/" class = "font-bold">LAKBAY</NuxtLink>
                <ul class = "flex gap-4">
                    <li><NuxtLink to = "/" class = "btn1" v-on:click = "logout">Logout</NuxtLink></li>
                    
                </ul>
            </nav>
        </header>
        

        <div class = "container mx-auto p-4">
            <slot />
        </div>
    </div>
</template>

<script>
import Cookies from 'js-cookie'
    export default{
        data(){
            return{
                authToken: "",
            }
            
        },
        methods: {
            logout(){
                console.log('deleting cookie')
                Cookies.remove('auth_token'); 
                this.authToken = ''
                
            }
        }
    }
</script>

<style scoped>
    .router-link-exact-active{
        color: #12b488;
    }
</style>