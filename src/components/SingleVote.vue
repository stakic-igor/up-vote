<script setup>

const emit = defineEmits(['upVote', 'id'])

const props = defineProps({
    submissions: {
        type: Array,
        required: true
    }
});

const upVote = (id) => {
    emit('upVote', id)
}

</script>

<template>
    <div 
        v-for="(submission, index) in submissions" :key="index"
        class="border border-gray-300 p-4 rounded mb-4 w-[80%] mx-auto">
        <div class="flex items-top">
            <img
                class="w-16 h-16 rounded-full mr-4" 
                :src="submission.avatar" 
            />
            <div class="mr-4">
                <h3 class="text-lg">{{ submission.title }}</h3>
                <p class="text-sm">{{ submission.description }}</p>
                <div class="flex flex-ro mt-1.5">
                    <p class="text-gray-500 text-xs items-center">{{ submission.author }}</p>
                    <span class="mx-2 text-gray-500 text-xs">|</span>
                    <p class="text-gray-500 text-xs">{{ submission.date }}</p>
                </div>
            </div>
            <div class="flex flex-col items-center ml-auto ">
                <p class="text-gray-500 text-sm">Votes:&nbsp;{{ submission.votes }}</p>
                <button 
                    class="bg-blue-500 text-white px-2 py-1 rounded cursor-pointer hover:bg-blue-600 mt-2" 
                    @click="upVote(submission.id)">
                    Vote
                </button>
            </div>
        </div>
    </div>
</template>
