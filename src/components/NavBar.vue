<script setup>
import { ref } from 'vue'
import { useAuth } from '@/composables/useAuth'


const{ isAuthenticated, logout, user } = useAuth()



const brand= ref(' 🏢 Company Directory 🏢')
</script>



<template>
<nav>
    <div class="wrapper">
    <RouterLink :to="{ name: 'Home' }" class="brand">
    <span class="brand-title">{{  brand }}</span>
    </RouterLink>
    <div class="menu">
        <p v-show="isAuthenticated" class="px-2 py-4">
          Welcome back
          <strong>
            <i>{{ user?.name }}</i>
          </strong>
        </p>
        <div v-if="isAuthenticated">
        <RouterLink :to="{ name: 'Setting'}" href="#" class="menu-item">Settings</RouterLink>

        <button class="menu-logout" @click="logout">Logout</button>
        </div>

        
        <div v-else>
        <RouterLink :to="{ name: 'Login'}" href="#" class="menu-login">Login</RouterLink>
        </div>
        
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
        & div {
            @apply py-2;
        }
        &-item {
            @apply rounded-md px-4 py-2 hover:bg-yellow-500 hover:text-blue-600;
        }
        &-login {
            @apply rounded-md px-4 py-2 hover:bg-green-500 bg-green-700 text-slate-200;
        }
        &-logout {
            @apply rounded-md  mx-4 px-4 py-2 hover:bg-red-500 bg-red-700 text-slate-200;
        }
    }
}

</style>