<script setup lang="ts">
import { joinURL } from 'ufo'
const { data: page } = await useAsyncData('index', () => queryContent('/').findOne())

const videoModalOpen = ref(false)

const site = useSiteConfig()
useSeoMeta({
  title: 'Hoda Eyes: Where Beauty Meets Convenience and Community',
  ogTitle: 'Hoda Eyes: Where Beauty Meets Convenience and Community',
  description: 'Discover Hoda Eyes, your go-to destination for top-quality nails and eyelash services. Whether you\'re looking for at-home beauty treatments or professional training, we\'ve got you covered. Join our community and experience beauty, quality, and convenience like never before.',
  ogImage: joinURL(site.url, '/social.jpg'),
  twitterImage: joinURL(site.url, '/social.jpg')
})

</script>

<template>
  <div v-if="page">
    <ULandingHero :ui="{ base: 'relative z-[1]' }" class="dark:bg-gradient-to-b from-gray-950 to-gray-900" v-bind="page.hero">
      <template #top>
        <HomeHeroBackground class="absolute -top-[--header-height] inset-x-0 w-full hidden lg:block" />
      </template>

      <template #title>
        Welcome to<br><span class="text-primary block lg:inline-block">Hoda Eyes Project</span>
      </template>

      <template #description>
        Tired of subpar nail and eyelash services in Dubai? Hoda Eyes has the solution you've been looking for. We specialize in nail and eyelash services, delivered by highly experienced and talented professionals dedicated to enhancing your beauty.
        
      </template>

      <template #links>
        <HomeSectionFor class="justify-center flex " />
      </template>

      <ULandingLogos :title="page.logos.title" class="mt-32 text-gray-500 dark:text-gray-400">
        <!-- Replace these logo components with your own -->
        <BrandsGithub class="h-7" />
        <BrandsOpenai class="h-5" />
        <BrandsNasa class="h-4" />
        <BrandsGoogle class="h-5" />
        <BrandsFedora class="h-4" />
        <BrandsGitlab class="h-4" />
        <BrandsUpwork class="h-8" />
      </ULandingLogos>
    </ULandingHero>

    <!-- Add more sections as needed -->
    <!-- eslint-disable vue/no-deprecated-slot-attribute -->
    <ULandingSection
      v-for="(section, index) of page.sections"
      :key="index"
      :slot="section.slot"
      :class="section.class"
      :align="section.align"
      :links="section.links"
    >
      <template #title>
        <!-- eslint-disable-next-line vue/no-v-html -->
        <span v-html="section?.title" />
      </template>

      <template v-if="section.description" #description>
        <!-- eslint-disable-next-line vue/no-v-html -->
        <span v-html="section.description" />
      </template>

      <template #features>
        <HomeSectionFeatures :features="section.features" />
      </template>

      <template #integrations>
        <HomeSectionIntegrations :integrations="section.integrations" />
      </template>

      <template #contributors>
        <HomeSectionContributors />
      </template>

      <template #testimonials>
        <HomeSectionTestimonials :testimonials="section.testimonials" />
      </template>

      <template #code>
        <MDC
          v-if="section.code"
          :value="section.code"
          tag="pre"
          class="prose prose-primary dark:prose-invert max-w-none"
          :parser-options="{
            highlight: {
              theme: {
                light: 'material-theme-lighter',
                default: 'material-theme',
                dark: 'material-theme-palenight'
              }
            }
          }"
        />
      </template>
    </ULandingSection>
  </div>
</template>

