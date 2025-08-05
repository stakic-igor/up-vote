<script setup>
import SingleVote from './components/SingleVote.vue';
import submissions from './seed.js'


</script>

<template>
  <h2>Up Vote</h2>
  {{ submissions[0].author }}
  <SingleVote />
</template>


