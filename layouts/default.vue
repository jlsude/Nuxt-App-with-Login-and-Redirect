<template>
    <div>
        <header class = "shadow-sm bg bg-mine-shaft-800">
            <nav class = "container mx-auto p-4 flex justify-between">
                <NuxtLink to = "/" class = "font-bold">LAKBAY</NuxtLink>
                <ul class = "flex gap-4">
                    <li><NuxtLink to = "/" class = "btn1">About</NuxtLink></li>
                    <li><NuxtLink to = "/Login" class = "btn1">Login</NuxtLink></li>
                    <li><NuxtLink to = "/Signup" class = "btn1">Signup</NuxtLink></li>
                </ul>
            </nav>
        </header>

        <div class = "container mx-auto p-4">
            <slot />
        </div>
    </div>
</template>

<script setup>

</script>

<style scoped>
    .router-link-exact-active{
        color: #ffffff;
    }
</style>