<script setup>
import { ref } from 'vue'
const brand= ref(' 🏢 Company Directory 🏢')
</script>



<template>
<nav>
    <div class="wrapper">
    <RouterLink :to="{name:'Home'}" class="brand">
    <span class="brand-title">{{  brand }}</span>
    </RouterLink>
    <div class="menu">
        <a href="#" class="menu-item">Department</a>
        <a href="#" class="menu-item">Settings</a>
        <a href="#" class="menu-login">Logout</a>
    </div>
    </div>
</nav>

</template>



<style scoped lang="postcss">
nav {
    @apply h-20 flex bg-blue-600 text-slate-400;
    .wrapper {
        @apply container mx-auto w-full flex items-center justify-between;
        .brand {
            &-title {

            
            @apply text-2xl font-bold text-green-500;
            }
        }
    }
    .menu {
        @apply flex gap-2;
        &-item {
            @apply rounded-md px-4 py-2 hover:bg-green-500 hover:text-blue-600;
        }
        &-login {
            @apply rounded-md px-4 py-2 hover:bg-red-500 bg-red-700 text-slate-200;
        }
    }
}

</style>