<script setup lang="ts">

import { ref, onMounted, onBeforeUnmount } from 'vue'
const showButton = ref(false)
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const handleScroll = () => {
  showButton.value = window.scrollY > 600
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll)
})
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
    <div v-if="showButton" class="fixed bottom-40 right-4 z-50">
      <UButton icon="i-lucide-arrow-up" color="gray" @click="scrollToTop">
        Top
      </UButton>
    </div>
  </UMain>

  <AppFooter />

  <UNotifications />
</template>
