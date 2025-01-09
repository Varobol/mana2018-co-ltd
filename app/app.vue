<script setup lang="ts">
useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: 'https://failfast.blob.core.windows.net/upload/Logo_manaForm.png' },
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

useSeoMeta({
  ogImage: 'https://failfast.blob.core.windows.net/upload/webmana/webmana.png',
})
</script>

<template>
  <AppHeader />

  <UMain>
    <NuxtPage />
  </UMain>

  <AppFooter />

  <UNotifications />
</template>
