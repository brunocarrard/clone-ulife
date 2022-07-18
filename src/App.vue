<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from './components/HelloWorld.vue'
import LoginForm from './components/LoginForm.vue'
</script>

<template>
<div class="content d-md-flex">
  <div class="left ">
  </div>
  <div class="right d-flex align-items-center justify-content-center">
    <LoginForm />
  </div>
</div>
</template>

<style scoped>
.content {
  background: linear-gradient(115deg, #dbe830 0%, #06cef0 40%, #28a1fd 70%) #06cef0;
}
.left {
  background: url("https://staticcdn.ulife.com.br/App_Themes/Content/logoCircle.svg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 40vh;
  width: 48%;
  height: 100vh;
}
.right {
  background: url("https://staticcdn.ulife.com.br/App_Themes/Content/whiteCircle.svg");
  background-repeat: no-repeat;
  background-position: left;
  background-size: 220vh;
  width: 52%;
  height: 100vh;
  padding-left: 2%;
}
@media only screen and (max-width: 768px) {


  .main {
    padding-top: 15% !important;
  }
    .right {
      background-position: 50% 0.2%;
      background-size: 200vh;
      height: 80%;
      width: 100%;
    }
    .left {
      display: block;
      height: 20%;
      width: 100%;
      background-size: 30vh;
    }
}
</style>
