<script setup>
import { onMounted } from 'vue';
import SingleVote from './components/SingleVote.vue';
import submissions from './seed.js'


onMounted(() => {
  
});

</script>

<template>
  <h1 class="text-2xl text-center pt-2 pb-4">Up Vote</h1>
  <SingleVote :submissions="submissions" />
</template>


