<template>
  <button @click="handleGoogle">Google</button>
 <div>Home</div>
</template>

<script setup lang="ts">
const handleGoogle = () => {
const baseUrl = "http://minddaily.joshibbotson.com:8082";
const redirectUri = `${baseUrl}/auth/google`;
window.location.href = redirectUri;
}
</script>

