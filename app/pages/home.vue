<template>
  <div>


    <UPage>
      <UPageBody>
        <ULandingSection class="bg-gray-200 ">
          <UPageHero title="Simpler, Faster, Safer" :ui="{ title: 'lg:text-6xl' }"
            description="Experience seamless payments with Mana—no banks, no delays, just full control over your money."
            :links="[{ label: 'JOIN NOW', color: 'red', size: 'lg' }]" align="left">
            <img src="https://failfast.blob.core.windows.net/upload/mobilemana.png"
              class="w-1/2 rounded-md   dark:ring-gray-700 justify-self-end " />
            <!-- justify-self right -->
          </UPageHero>
        </ULandingSection>

        <ULandingSection :ui="{ wrapper: 'p-9 sm:p-0 ' }" class="-mt-[128px]">
          <iframe width="100%" height="680"
            src="https://www.youtube.com/embed/koGdfT1Scgo?si=bWfsiKRyy3dVD4US&amp;controls=0" frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin"></iframe>
        </ULandingSection>

        <ULandingSection title="Why mana"
          description="Having a solution isn't enough—it needs to be efficient, reliable, and adaptable. Mana offers a flexible platform with unique features, ensuring every transaction is fast, secure, and perfectly tailored to your needs.">
          <UPageGrid id="features" class="scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
            <ULandingCard v-for="(item, index) in itemFeature" :key="index" v-bind="item" />
          </UPageGrid>
        </ULandingSection>

        <ULandingSection title="Testimonials" :ui="{ wrapper: 'p-9 sm:p-0 ' }">
          <UPageColumns id="testimonials" class="xl:columns-4 scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
            <div v-for="(testimonial, index) in dataTestimonials" :key="index" class="break-inside-avoid">
              <ULandingTestimonial v-bind="testimonial" />
            </div>
          </UPageColumns>
        </ULandingSection>

        <ULandingSection id="faq" title="Frequently Asked Questions"
          description="Discover how Mana helps you manage payments with ease and flexibility. Here are the most common questions.">
          <ULandingFAQ id="faq"  :items="itemsFaq" multiple />
        </ULandingSection>

      </UPageBody>
    </UPage>
  </div>
</template>

<script setup lang="ts">
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne());
const itemFeature = ref([
  {
    "title": "Multi-Currency Wallet",
    "description": "Mana is an omni-wallet that allows users to securely store, send, and receive multiple currencies, both fiat and crypto, and exchange between them within the wallet. With Mana, you can easily manage all your funds in one convenient place.",
    "icon": "i-heroicons-cog"
  },
  {
    "title": "Zero Transaction Fees",
    "description": "Mana has no transaction fees, making it a cost-effective choice for individuals and businesses alike.",
    "icon": "i-heroicons-check"
  },
  {
    "title": "One-Stop-Super App",
    "description": "With Mana, you don't need multiple apps to manage your finances or access third-party services. Seamlessly integrate budgeting tools, investment apps, and more into your omni-wallet.",
    "icon": "i-heroicons-lock-closed"
  },
  {
    "title": "Customized End-to-End Service",
    "description": " At Mana, we provide a personalized end-to-end service tailored to your unique business needs, from initial contact to after-service.",
    "icon": "i-heroicons-rocket-launch"
  },
  {
    "title": "Maximum Privacy and Security",
    "description": "Mana's blockchain-based ledger ensures the highest level of privacy and security for all user data, including personal information and transaction records, with no access by the wallet provider or any third parties without explicit user consent.",
    "icon": "i-heroicons-currency-dollar"
  }
]);

const dataTestimonials = ref([{
  quote: 'Onboarding with Mana was incredibly simple. No more tedious paperwork or compliance headaches—just a seamless connection to the platform. We were up and running in no time, and Mana took care of everything behind the scenes, allowing us to focus on what matters most." - Siriwasan Akanitthaphichat, CTO at Jergun',
  author: {
    name: 'Evan you',
    job: 'Creator of Vue.js and Vite',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/yyx990803'
    }
  }
}, {
  quote: 'As a third-party developer working with various business requirements, Mana\'s API truly impressed me. Its flexibility caters to different business needs, offering a wide range of commands that go beyond what other financial platforms provide. Features like real-time revenue sharing are a game-changer, making Mana the perfect solution for any client I work with. - Sakul Jaruthanaset, Independent Software Developer',
  author: {
    name: 'Guillermo Rauch',
    job: 'Co-founder and CEO of Vercel',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/rauchg'
    }
  }
}
  , {
  quote: 'With Mana, I no longer have to worry about constantly checking my employees’ work or the money coming in each day. The platform’s automation ensures that everything is handled seamlessly, and if there’s ever a mistake, the transaction won’t even trigger. It’s a relief knowing that everything is managed securely and automatically, giving me more time to focus on growing my business. - Tanyanan Kiatsuranon, Business Owner',
  author: {
    name: 'Addy Osmani',
    job: 'Chief Engineer of Chrome',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/addyosmani'
    }
  }
}
  , {
  quote: 'Before using Mana, settling payments between restaurants and riders was a constant hassle. Now, with Mana’s conditional transactions, everything is done automatically. I don’t have to manually handle any of it, which has been such a time-saver and makes my job so much easier. - Orawan Permsree, Food Delivery Administrator at Solar Delivery',
  author: {
    name: 'Sarah Drasner',
    job: 'Director of Engineering, Google',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/sdras'
    }
  }
}, {
  quote: 'With traditional bank services, I could only process payroll once a month, and it came with fees. But with Mana, I have the flexibility to manage payroll anytime. I’m also able to automatically track and collect any payroll advances made by employees—all with just a one-time setup. It’s a game-changer for HR management." - Tippawan Sayoomporn, HR at Prompiman Hotel',
  author: {
    name: 'Dominik Angerer',
    job: 'Co-founder of Storyblok',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/DominikAngerer'
    }
  }
}, {
  quote: 'Running a night pub means constantly managing promotions, which used to be a headache. Thanks to Mana’s coupon features, I just set the rules for each promotion, and everything runs automatically—without any errors! It’s made managing promotions so much easier and stress-free." - Chanawee Jittumnan, Manager at iBAR',
  author: {
    name: 'Savas Vedova',
    job: 'Sernior Frontend Engineer at GitLab',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/svedova'
    }
  }
}, {
  quote: 'Mana isn’t just about payments—it comes with a full restaurant management system, including POS and online menu integration. Now, I can handle all aspects of daily operations with ease, using the same tools as big chains but at a much lower cost. It’s made running the restaurant so much smoother. - Charinrat Jantawee, Manager at SIT',
  author: {
    name: 'Savas Vedova',
    job: 'Sernior Frontend Engineer at GitLab',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/svedova'
    }
  }
}, {
  quote: 'Nothing beats getting paid in real-time. - (Ask Whan), Freelancer Rider',
  author: {
    name: 'Savas Vedova',
    job: 'Sernior Frontend Engineer at GitLab',
    avatar: {
      src: 'https://ipx.nuxt.com/f_auto,s_40x40/gh_avatar/svedova'
    }
  }
}
]);

const itemsFaq = [{
  label: 'What is Mana Platform?',
  content: 'Mana is a decentralized financial platform designed to simplify payments. Whether you’re a user, a business, or a developer, Mana offers seamless, secure transactions with unique features like real-time revenue sharing and conditional transactions.'
}
  , {
  label: 'Is Mana Platform licensed?',
  content: 'Yes, Mana is fully licensed by the Central Bank of Thailand, ensuring our services comply with strict regulatory standards, providing you with a legitimate and trusted platform.'
}, {
  label: 'How do I get started with Mana?',
  content: 'Download the Mana app from the App Store or Google Play, create an account, and start using it right away. If you’re a business or developer, you can register through the app to access advanced features like integration and payment management.'
}, {
  label: 'Is Mana secure?',
  content: 'Absolutely. Mana leverages blockchain technology to ensure all transactions are secure, transparent, and tamper-proof, giving you peace of mind.'
}, {
  label: 'Does Mana handle compliance and regulations for me?',
  content: 'Yes, for businesses and developers, Mana takes care of compliance and regulatory requirements, so you can focus on growing your business without worrying about paperwork or bank integrations.'
}, {
  label: 'Can I use Mana for real-time revenue sharing?',
  content: 'Yes, Mana’s platform supports real-time revenue sharing, making it easy to instantly distribute funds to multiple recipients based on your customized conditions.'
}, {
  label: 'What makes Mana different from other payment platforms?',
  content: 'Mana is flexible and designed for both users and businesses. It offers unique features like conditional transactions and real-time payment processing, simplifying complex financial tasks without additional hassle.'
}, {
  label: 'Is there a fee for using Mana?',
  content: 'Mana offers competitive pricing with no hidden fees. Basic services are free for users, and businesses only pay for the features they use, ensuring cost-effective solutions.'
},
]

useSeoMeta({
  title: page.value.title,
  ogTitle: page.value.title,
  description: page.value.description,
  ogDescription: page.value.description
})

</script>