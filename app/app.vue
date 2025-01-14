<script setup lang="ts">
const { data: page } = await useAsyncData('', () => queryContent('/').findOne());

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
  title: page.value.title,
  ogTitle: page.value.title,
  description: "Simpler Faster Safer",
  ogDescription: "Simpler Faster Safer",
  ogImageUrl: "https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png",
  ogImageHeight: 630,
  ogImageWidth: 1200
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
