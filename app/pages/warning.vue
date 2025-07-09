<template>
  <div>
    <UPage>
      <UPageBody :ui="{ wrapper: 'mt-0 pb-0' }">
        <img src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption01.png" />
        <p class="p-6 text-3xl font-bold  text-center">รู้ให้ทันภัยการเงิน</p>
        <img class="lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption02.png" />
        <p class="p-6 text-3xl font-bold  text-center">อย่าเชื่อ อย่าโอน</p>
        <img class="lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption03.png" />
        <p class="p-6 text-3xl font-bold  text-center">ยกระดับการจัดการบัญชีม้า</p>
        <img class="lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption04.png" />
        <p class="p-6 text-3xl font-bold  text-center">แจ้งเหตุทันที</p>
        <img class="lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption05.png" />
        <p class="p-6 text-3xl font-bold  text-center">แฉกลโกง มิจฉาชีพ</p>
        <img class="pb-6 lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption06.png" />
        <img class="pb-6 lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption07.png" />
        <img class="pb-6 lg:px-64  px-6"
          src="https://failfast.blob.core.windows.net/upload/webmana/warning/anti-corruption08.png" />
      </UPageBody>
    </UPage>
  </div>
</template>

<script setup lang="ts">
const route = useRoute()
onMounted(() => {
  console.log('Current route:', route.path);
})

useSeoMeta({
  title: "mana2018",
  ogTitle: "mana2018",
  description: "Simpler Faster Safer!",
  ogDescription: "Simpler Faster Safer!",
  ogImage: "https://failfast.blob.core.windows.net/upload/webmana/Logo_manaForm.png",
})

</script>
