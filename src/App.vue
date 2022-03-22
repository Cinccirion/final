<template>
<P>HELLO</P>
<Auth/>
  <section>
    <router-view class="app-main" /> <!-- your routes will load inside of these tags -->    
  </section>


  
  
</template>

<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import { onMounted } from 'vue'
import { storeToRefs } from 'pinia'
import { useRouter } from 'vue-router'
import { useUserStore } from './store/user.js'
import { createApp } from "vue";
import Auth from './views/Auth.vue'


const userStore = useUserStore()
const { user } = storeToRefs(userStore)



onMounted(async () => {
  try {
    await userStore.fetchUser() // here we call fetch user
    if (!user.value) {
      // redirect them to logout if the user is not there
      router.push({ path: '/auth' });
    } else {
      // continue to dashboard
      router.push({ path: '/' });
    }
  } catch (e) {
    console.log(e)
  }
})
</script>

















