<script setup lang="ts">
const nuxtApp = useNuxtApp()
const { activeHeadings, updateHeadings } = useScrollspy()

const links = computed(() => [{
  label: 'Features',
  to: '#features',
  icon: 'i-heroicons-cube-transparent',
  active: activeHeadings.value.includes('features') && !activeHeadings.value.includes('testimonials')
}, {
  label: 'Testimonials',
  to: '#testimonials',
  icon: 'i-heroicons-academic-cap',
  active: activeHeadings.value.includes('testimonials') && !activeHeadings.value.includes('faq')
}, {
  label: 'FAQ',
  to: '#faq',
  icon: 'i-heroicons-question-mark-circle',
  active: activeHeadings.value.includes('faq')
}])

// nuxtApp.hooks.hookOnce('page:finish', () => {
//   updateHeadings([
//     document.querySelector('#features'),
//     document.querySelector('#testimonials'),
//     document.querySelector('#faq')
//   ])
// })



</script>

<template>
  <UHeader :links="links">
    <template #logo>
      <UAvatar size="sm" src="https://failfast.blob.core.windows.net/upload/Logo_manaForm.png" />
      mana
    </template>

    <template #right>
      <UButton label="ป้องกันภัยทุจริต" color="white" class="hidden lg:flex"
        @click="$router.push('/warning'), { replace: true }" />
    </template>

    <template #panel>
      <UAsideLinks v-if="$router.currentRoute.value.path === '/'" :links="links" />
      <UAsideLinks v-else :links="[{
        label: 'Home',
        to: '/',
        icon: 'i-heroicons-home'
      }]" />

      <UDivider class="my-6" />
      <!-- <UButton label="Sign in" color="white" block class="mb-3" /> -->
      <UButton label="ป้องกันภัยทุจริต" color="white" block class="mb-3" @click="$router.push('/warning')" />
    </template>
  </UHeader>
</template>
