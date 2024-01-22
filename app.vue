<template>
  <nav class="p-4 md:px-6 bg-black text-white">
    <ul class="flex flex-row gap-2 items-start">
      <li class="flex-auto">
        <NuxtLink to="/" target=""> Nuxt View Transitions Demo </NuxtLink>
      </li>
      <li>
        <NuxtLink to="https://nuxt.com" target="_blank">
          <img class="h-5" src="https://nuxt.com/assets/design-kit/logo/full-logo-green-light.svg" />
        </NuxtLink>
      </li>
    </ul>
  </nav>
  <main class="md:p-6 p-4">
    <NuxtPage />
  </main>
</template>
