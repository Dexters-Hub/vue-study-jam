<script>
import MovieLayout from './components/MovieLayout.vue'
import FilterComp from './components/FilterComp.vue'
import SearchComp from './components/SearchComp.vue'
export default {
  components: {
    MovieLayout,
    FilterComp,
    SearchComp
  },
  data() {
    return {
      movies: [
        {
          id: 1,
          title: 'Premam',
          actor: 'Nivin Pauly',
          rating: 4.5,
          poster: 'https://m.media-amazon.com/images/M/MV5BMzJhNjMyOGMtYjhiYy00ZTAwLThmZWUtZmE5NzI3OTk4Y2M4XkEyXkFqcGdeQXVyMzQ5Njc3NzU@._V1_.jpg'
        },
        {
          id: 2,
          title: 'Drishyam',
          actor: 'Mohanlal',
          rating: 9.1,
          poster: 'https://m.media-amazon.com/images/M/MV5BM2RiZDVjYWEtZGNhYy00ZGU0LTgwZjMtZTJmNmMyNGQ5NGYyXkEyXkFqcGdeQXVyNjY1MTg4Mzc@._V1_.jpg'
        },
        {
          id: 3,
          title: 'Kumbalangi Nights',
          actor: 'Fahadh Faasil',
          rating: 8.7,
          poster: 'https://m.media-amazon.com/images/M/MV5BNjU5MmQwMWYtMGFiMS00NTRiLThiODAtMzNkNzU1MWNjYTllXkEyXkFqcGdeQXVyMjkxNzQ1NDI@._V1_.jpg'
        },
      ]
    }
  },
  methods:{
        // filtering
        filterMovies(){
          console.log("ruNNING")
            this.movies = this.movies.filter(movie => movie.rating < 8)
        },

        // searching
        searchMovies(name){
          console.log("App running search", name)
          this.movies = this.movies.filter(movie => movie.title.toLowerCase().includes(name.toLowerCase()))
        }
    }
}
</script>

<template>
  <!-- main container -->
  <div class="container mx-auto px-4">
    <!-- header -->
    <header class="flex items-center justify-between py-4">
      <h1 class="text-3xl font-semibold">Movie App</h1>
    </header>
    <!-- main content -->
    <main>
      <!-- movie layout -->
      <!-- filtering -->
      <div class="flex space-x-4">
        <SearchComp @search="searchMovies" />
        <FilterComp @filter="filterMovies" /></div>
        
      
      <MovieLayout :movies="movies" />
    </main>
    </div>
</template>
