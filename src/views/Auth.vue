<template>
<div>
<div>
    <h1>Welcome to the Vue Task App</h1>
</div>
<div>
<SignIn v-if="component"/>
<SignUp v-else/>    
</div>
<div class="Sign-buttons">
    <h4>Have you already got an acount?</h4>
    <button @click="changeSign" v-if="component">Sign In</button>
    <button @click="changeSign" v-else >Sign Up</button>
</div>
</div>
</template>

<script setup>
import { ref } from "vue"
import SignIn from "../components/SignIn.vue"
import SignUp from "../components/SignUp.vue"

import router from "../router/index"

const component = ref (false)

function changeSign(){
    component.value= !component.value;
}


</script>

<style>

</style>