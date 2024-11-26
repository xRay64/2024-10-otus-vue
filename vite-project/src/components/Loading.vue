<script setup>
defineProps(['active'])
</script>

<template>
  <div v-if="active" class="h-64 grid place-content-center">
    <img src="../assets/loading.gif" alt="">Loading
  </div>
</template>