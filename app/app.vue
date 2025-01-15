<script setup lang="ts">
useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: 'https://failfast.blob.core.windows.net/upload/webmana/Logo_mana.png' },
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

useSeoMeta({
  title: 'mana2018',
  description: 'Simpler Faster Safer!',
  ogDescription: 'Simpler Faster Safer!',
  ogImage: 'https://failfast.blob.core.windows.net/upload/webmana/Logo_mana.png',
  twitterImage: 'https://failfast.blob.core.windows.net/upload/webmana/Logo_mana.png',
  twitterCard: 'summary_large_image',
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
