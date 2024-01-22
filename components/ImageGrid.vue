<script setup>
const config = useRuntimeConfig();
const { data: movies } = await useFetch("/tmdb/tv/popular", {
  baseURL: config.public.imageApi,
  query: {
    page: 1,
    language: "en",
  },
});

// Used useState as data is shared accoss pages
const active = useState();
</script>

<template>
  <section class="grid grid-cols-4 md:grid-cols-6 gap-4">
    <article v-for="movie in movies.results">
      <NuxtLink :to="`/movie/${movie.id}`" @click.native="active = movie.id">
        <NuxtImg
          v-if="movie.poster_path"
          width="400"
          height="600"
          format="webp"
          :src="`/tmdb${movie.poster_path}`"
          :alt="movie.title || movie.name"
          class="w-full h-full object-cover rounded hover:scale-[1.03] transition ease-in duration-300"
          :class="{ active: active === movie.id }"
        />
      </NuxtLink>
    </article>
  </section>
</template>

<style scoped>
img.active {
  view-transition-name: selected-film;
  contain: layout;
}
</style>
