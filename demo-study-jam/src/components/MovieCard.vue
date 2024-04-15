<script>
export default{
    props: {
        movie: {
            type: Object,
            required: true
        }
    }
}
</script>
<template>
    <div class="flex flex-col items-center justify-center">
    
        <a href="https://google.com"><img :src="movie.poster" alt="movie.title" class="w-48 h-72 object-cover rounded-lg"></a> 
        <h2 class="text-lg font-semibold mt-4">{{ movie.title }}</h2>
        <p class="text-sm text-gray-500">{{ movie.actor }}</p>
        <!-- rating -->
        <div class="flex items-center mt-2">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 text-yellow-500" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd"
                    d="M10 2a1 1 0 0 1 1 1v5.586l2.293-2.293a1 1 0 0 1 1.414 1.414l-3 3a1 1 0 0 1-1.414 0l-3-3a1 1 0 1 1 1.414-1.414L9 8.586V3a1 1 0 0 1 1-1zm0 8a1 1 0 0 1 1 1v5.586l2.293-2.293a1 1 0 0 1 1.414 1.414l-3 3a1 1 0 0 1-1.414 0l-3-3a1 1 0 1 1 1.414-1.414L9 13.586V10a1 1 0 0 1 1-1z"
                    clip-rule="evenodd" />
            </svg>
            <span class="text-sm text-gray-500 ml-1">{{ movie.rating }}</span>
        </div>

        <!-- A spce for dialog which is audio -->
        <div class="mt-4">
            <audio controls>
                <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
                Your browser does not support the audio element.
            </audio>
        </div>
    </div>
</template>