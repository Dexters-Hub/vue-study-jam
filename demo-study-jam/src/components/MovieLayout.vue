<script>
import MovieCard from './MovieCard.vue'

export default{
    components: {
        MovieCard
    },
    props: {
        movies: {
            type: Array,
            required: true
        }
    },

    
   
}
</script>

<template>
    <!-- Movie layout which renders a list of movies -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 p-8">
        
        <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie" />
    </div>
</template>