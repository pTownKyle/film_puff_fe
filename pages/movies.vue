<template>
  <main class="flex flex-col items-center justify-center h-full">
    <h1 class="text-3xl mb-3">Film Puff Movies</h1>
    <select class="mb-3" v-model="selectedGenre">
      <option disabled value="">Choose A Genre</option>
      <option v-for="genre in movieGenres" :key="genre" :value="genre">
        {{ genre }}
      </option>
    </select>
    <div class="flex justify-between border-b-2 border-gray-900 w-full mb-2">
      <p>Movie Name</p>
      <p>Release Year</p>
    </div>
    <ul class="overflow-y-auto h-3/4 w-full space-y-2 px-3 mb-6">
      <li
        v-for="movie in movieData.body"
        :key="movie['Movie Name'] + movie['Release Date']"
        v-if="movie['Genre'] == selectedGenre"
      >
        <div
          class="flex justify-between cursor-pointer"
          @click="getMovie(movie)"
        >
          <p>{{ movie['Movie Name'] }}</p>
          <p class="ml-3">{{ movie['Release Date'] }}</p>
        </div>
      </li>
    </ul>

    <!-- <div
      class="h-20 bg-gray-200 w-full fixed bottom-8 flex items-center space-x-1 px-1"
    >
      <div class="" v-for="(genre, index) of movieGenres" :key="index">
        <button class="text-xs py-3" @click="changeGenre(genre)">
          {{ genre }}
        </button>
      </div>
    </div> -->
  </main>
</template>

<script>
export default {
  async asyncData({ $content }) {
    // Setup & Get Movie Data
    const movieData = await $content('reefer_movies').fetch()
    // Setup List of Movie Genres

    return { movieData }
  },
  data() {
    return {
      movieGenres: [
        'Comedy',
        'Drama',
        'Sci-Fi, Fantasy, & Horror',
        'Action & Sports',
        'Animated',
        'Music',
        'Documentary',
      ],
      selectedGenre: '',
    }
  },
  methods: {
    changeGenre(genre) {
      this.currentGenre = genre
    },
    getMovie(movie) {
      console.log(`${movie['Movie Name']} \t ${movie['Release Date']}`)
    },
  },
}
</script>
