<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())
const data = ref([{
  quote: 'Nostrud reprehenderit magna deserunt dolor.',
  author: {
    name: 'Evan you',
    job: 'Creator of Vue.js and Vite',
    src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/yyx990803'
  }
}, {
  quote: 'Irure irure dolore Lorem dolor anim velit id fugiat minim cupidatat dolore nulla Lorem aliquip cillum.',
  author: {
    name: 'Guillermo Rauch',
    job: 'Co-founder and CEO of Vercel',
    src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/rauchg'
  }
}, {
  quote: 'Magna labore amet velit eiusmod velit dolor cillum sunt est tempor ea commodo fugiat amet tempor.',
  author: {
    name: 'Addy Osmani',
    job: 'Chief Engineer of Chrome',
    src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/addyosmani'
  }
}, {
  quote: 'Culpa amet do sit officia non magna cillum ullamco dolore qui sunt occaecat.',
  author: {
    name: 'Sarah Drasner',
    job: 'Director of Engineering, Google',
    src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/sdras'
  }
}, {
  quote: 'Ex veniam eu incididunt.',
  author: {
    name: 'Dominik Angerer',
    job: 'Co-founder of Storyblok',
    src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/DominikAngerer'
  }
}, {
  quote: 'Nostrud id Lorem laborum ut eiusmod voluptate aliquip non esse sint occaecat.',
  author: {
    name: 'Savas Vedova',
    job: 'Sernior Frontend Engineer at GitLab',
    src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/svedova'
  }
}
]);
useSeoMeta({
  title: page.value.title,
  ogTitle: page.value.title,
  description: page.value.description,
  ogDescription: page.value.description
})
</script>

<template>
  <div>
    <!-- <ULandingHero
      :title="page.hero.title"
      :description="page.hero.description"
      :links="page.hero.links"
    >
      <template #headline>
        <UBadge
          v-if="page.hero.headline"
          variant="subtle"
          size="lg"
          class="relative rounded-full font-semibold"
        >
          <NuxtLink
            :to="page.hero.headline.to"
            target="_blank"
            class="focus:outline-none"
            tabindex="-1"
          >
            <span
              class="absolute inset-0"
              aria-hidden="true"
            />
          </NuxtLink>

          {{ page.hero.headline.label }}

          <UIcon
            v-if="page.hero.headline.icon"
            :name="page.hero.headline.icon"
            class="ml-1 w-4 h-4 pointer-events-none"
          />
        </UBadge>
      </template>

<ImagePlaceholder />

<ULandingLogos :title="page.logos.title" align="center">
  <UIcon v-for="icon in page.logos.icons" :key="icon" :name="icon"
    class="w-12 h-12 lg:w-16 lg:h-16 flex-shrink-0 text-gray-900 dark:text-white" />
</ULandingLogos>
</ULandingHero>

<ULandingSection :title="page.features.title" :description="page.features.description"
  :headline="page.features.headline">
  <UPageGrid id="features" class="scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
    <ULandingCard v-for="(item, index) in page.features.items" :key="index" v-bind="item" />
  </UPageGrid>
</ULandingSection>

<ULandingSection :title="page.pricing.title" :description="page.pricing.description" :headline="page.pricing.headline">
  <UPricingGrid id="pricing" compact class="scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
    <UPricingCard v-for="(plan, index) in page.pricing.plans" :key="index" v-bind="plan" />
  </UPricingGrid>
</ULandingSection>

<ULandingSection :headline="page.testimonials.headline" :title="page.testimonials.title"
  :description="page.testimonials.description">
  <UPageColumns id="testimonials" class="xl:columns-4 scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
    <div v-for="(testimonial, index) in page.testimonials.items" :key="index" class="break-inside-avoid">
      <ULandingTestimonial v-bind="testimonial" />
    </div>
  </UPageColumns>
</ULandingSection>

<ULandingSection class="bg-primary-50 dark:bg-primary-400 dark:bg-opacity-10">
  <ULandingCTA v-bind="page.cta" :card="false" />
</ULandingSection>

<ULandingSection id="faq" :title="page.faq.title" :description="page.faq.description"
  class="scroll-mt-[var(--header-height)]">
  <ULandingFAQ multiple :items="page.faq.items" :ui="{
          button: {
            label: 'font-semibold',
            trailingIcon: {
              base: 'w-6 h-6'
            }
          }
        }" class="max-w-4xl mx-auto" />
</ULandingSection> -->
    <UPageHero title="Official Support"
      description="Through NuxtLabs experts and agency networks, we have a solution for every need."
      :links="[{ label: 'JOIN NOW', color: 'red', size: 'lg' }]">
      >

    </UPageHero>

    <UPage>
      <UPageBody>
        <UPageCard title="Tailwind CSS"
          description="Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS."
          icon="i-simple-icons-tailwindcss" />


        <UPageColumns>
          <UPageCard v-for="(item, index) in data" :key="index">
            <q class="italic text-gray-500 dark:text-gray-400">
              {{ item.quote }}
            </q>

            <div class="flex gap-x-3 items-center mt-3">
              <UAvatar :src="item.author.src" :alt="item.author.name" size="sm" />

              <div class="min-w-0 text-sm">
                <p class="font-semibold">
                  {{ item.author.name }}
                </p>
                <p class="truncate">
                  {{ item.author.job }}
                </p>
              </div>
            </div>
          </UPageCard>
        </UPageColumns>
      </UPageBody>
    </UPage>
  </div>
</template>

