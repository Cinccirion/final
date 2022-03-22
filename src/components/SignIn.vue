<template>

<div class="signIn-container" >
<h2>Sign In</h2>
    <form class="signIn-intro">
         <span v-tooltip.tooltip="'Completa este campo'"></span>
    <input name="mail" type="mail" placeholder="Email" @hover="v-Tooltip"><br/>
        <span v-tooltip.tooltip="'Completa este campo'"></span>
    <input name="password" type="texholder" placeholder="Password" @hover="v-Tooltip"> <br/>

    <button>Log In</button>

    </form>


</div>

</template>

<script setup>
import Tooltip from "../components/Tooltip.vue";

</script>

<style>

</style>