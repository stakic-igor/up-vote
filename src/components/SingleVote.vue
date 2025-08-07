<script setup>
const props = defineProps({
    submissions: {
        type: Array,
        required: true
    }
});

const upVote = (id) => {
}

</script>

<template>
    <div class="border p-4 rounded mb-1" v-for="(submission, index) in submissions" :key="index">
        <div class="flex items-top mb-4">
            <img
                class="w-16 h-16 rounded-full mb-4 mr-4" 
                :src="submission.avatar" 
            />
            <div class="mr-4">
                <h3 class="text-lg">{{ submission.title }}</h3>
                <p class="text-sm">{{ submission.description }}</p>
            </div>
            <div class="flex flex-col items-center ml-auto ">
                <p class="text-gray-500 text-sm">Votes: {{ submission.votes }}</p>
                <button 
                    class="bg-blue-500 text-white px-2 py-1 rounded cursor-pointer hover:bg-blue-600 mt-2" 
                    @click="upVote(submission.id)">
                    Vote
                </button>
            </div>
        </div>
    </div>
</template>
