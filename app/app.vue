<script setup lang="ts">
useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: 'https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png' },
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

useSeoMeta({
  ogImage: 'https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png',
  twitterImage: 'https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png',
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
