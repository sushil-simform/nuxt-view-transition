<template>
  <nav class="p-4 md:px-6 bg-black text-white sticky top-0">
    <ul class="flex flex-row gap-2 items-start">
      <li class="flex-auto">
        <NuxtLink to="/" target=""> Nuxt View Transitions Demo </NuxtLink>
      </li>
    </ul>
  </nav>
  <main class="md:p-6 p-4">
    <NuxtPage />
  </main>
</template>
