<script setup>
const config = useRuntimeConfig();
const route = useRoute();
const { data: movie } = await useFetch(`/tmdb/tv/${route.params.slug}`, {
  baseURL: config.public.imageApi,
});
</script>

<template>
  <div class="flex flex-row gap-4">
    <NuxtImg
      v-if="movie.poster_path"
      width="400"
      height="600"
      format="webp"
      :src="`/tmdb${movie.poster_path}`"
      :alt="movie.title || movie.name"
      class="w-1/2 max-h-[75vh] object-cover rounded"
    />
    <div class="flex flex-col gap-3">
      <h1 class="font-bold text-lg">{{ movie.title || movie.name }}</h1>
      <p
        class="mt-2 op80 leading-relaxed of-hidden line-clamp-5 md:line-clamp-7 text-xs md:text-base"
      >
        {{ movie.overview }}
      </p>
      <p>
        <NuxtLink class="font-bold text-green-600 hover:underline" to="/">
          Back to gallery
        </NuxtLink>
      </p>
    </div>
  </div>
</template>

<style scoped>
h1 {
  view-transition-name: header;
}

img {
  view-transition-name: selected-film;
}
</style>

<style>
::view-transition-old(header),
::view-transition-new(header) {
  width: auto;
}
</style>
