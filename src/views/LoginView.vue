<script setup>
import Login from '../components/Login.vue'
</script>

<template>
    <main>
    <Login />
  </main>

      
  </template>
  
  <style>
  
   main{
    background-color: white;
    height: 90%;
    width: 100%;
  }
  
  @media (min-width: 1024px) {
    .login {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
  }
  </style>
  