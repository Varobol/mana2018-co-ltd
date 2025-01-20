<script setup lang="ts">
const links = [{
  label: 'Download',
  children: [{
    label: 'mana Application'
  }]
}]


const gotoIOS = async () => {
  const storeUrl = "https://apps.apple.com/th/app/mana/id1273112680";
  window.location.href = storeUrl;
}

const gotoAndoid = async () => {
  const storeUrl = "https://play.google.com/store/apps/details?id=thes.mana.client&pli=1";
  window.location.href = storeUrl;
}
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
          <UButton class="m-2 w-32  h-12 place-content-center" icon="i-cib-apple" @click="gotoIOS">App Store</UButton>
          <UButton class="m-2 w-32  h-12 place-content-center" icon="i-cib-google-play" @click="gotoAndoid">Google Pay
          </UButton>
        </template>
      </UFooterColumns>
    </template>
    <template #right>
    </template>
  </UFooter>
</template>
