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
  description: "What is mana??",
  ogDescription: "What is mana???",
  ogImage: "https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png",
  ogImageUrl: "https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png",
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
