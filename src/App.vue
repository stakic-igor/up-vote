<script setup>
import { computed, ref } from 'vue';
import SingleVote from './components/SingleVote.vue';
import submissions from './seed.js'

const subs = ref(submissions);

function handleUpVote(id) {
  const submission = subs.value.find(sub => sub.id === id);
  if (submission) {
    submission.votes++;
  }
}

const sortedSubmissions = computed(() => {
  return subs.value.sort((a, b) => b.votes - a.votes)
})

</script>

<template>
  <h1 class="text-2xl text-center pt-2 pb-4">Up Vote</h1>
  <SingleVote :submissions="sortedSubmissions"  @upVote="handleUpVote"/>
</template>


 