<script setup lang="ts">
const links = [{
  label: 'Download',
  children: [{
    label: 'mana Application'
  }]
}]
</script>

<template>
  <UFooter class="bg-red-600 " :ui="{
    wrapper: 'lg:border-none',
    top: { wrapper: 'border-none', container: 'p-2 lg:p-4 ' },
    bottom: { container: 'p-2 lg:p-4', wrapper: '' }
  }">
    <template #top>
      <UFooterColumns :ui="{
        list: 'p-0 m-0 ',
        base: 'text-4xl ',
        label: 'text-white dark:text-white text-4xl',
        active: 'text-blue-600 dark:text-blue-600 font-medium text-3xl',
        inactive: 'text-white dark:text-white hover:text-white dark:hover:text-white text-3xl',
      }" :links="links">
        <template #right>
          <UButton class="m-2 w-32  h-12 place-content-center" icon="i-cib-apple">App Store</UButton>
          <UButton class="m-2 w-32  h-12 place-content-center" icon="i-cib-google-play">Google Pay</UButton>
        </template>
      </UFooterColumns>
    </template>
    <template #right>
      <UColorModeButton size="sm" />
    </template>
  </UFooter>
</template>
