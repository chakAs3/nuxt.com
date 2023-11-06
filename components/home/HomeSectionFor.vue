<script setup lang="ts">
import { _backgroundImage } from '#tailwind-config/theme'


</script>

<template>
  <UPageGrid class="xl:grid-cols-4">
    <ULandingCard
      title="For Customers"
      description="Experience the beauty of perfectly manicured nails and stunning eyelashes in the comfort of your own space. We bring specialized nail and eyelash services to your doorstep."
      :ui="{
        background: 'dark:bg-gradient-to-b from-gray-700/50 to-gray-900/50',
        backgroundImage: 'url(/assets/for/1.png)',
        body: {
          base: 'flex-1',
          background: 'dark:bg-gray-900/50'
        }
      }"
      class="bg-white dark:bg-gray-900"
    >
      <div class="flex flex-col items-center justify-center">
        <UButton to="/book-home-service" icon="i-ph-calendar-check-duotone" size="xl">
          Book Home Service
        </UButton>
      </div>
    </ULandingCard>
    <ULandingCard
      title="For Technicians & Artists"
      description="Are you a nail or eyelash technician looking to take your career to the next level? We offer training and certification programs to help you become a professional nail or eyelash technician."
      :ui="{
        background: 'dark:bg-gradient-to-b from-gray-700/50 to-gray-900/50',
        backgroundImage: 'url(/assets/for/2.webp)',
        body: {
          base: 'flex-1',
          background: 'dark:bg-gray-900/50'
        }
      }"
    >
      <template #default>
        <div class="flex flex-col items-center justify-center">
          <UButton size="xl" color="white" icon="i-ph-plugs-connected-duotone" to="/training">
            Become a Professional
          </UButton>
        </div>
      </template>
    </ULandingCard>

    <ULandingCard
      title="For Beauty Salons"
      description="Say goodbye to staffing woes. We lease highly skilled nail and eyelash professionals on an hourly, daily, or monthly basis. Enjoy the flexibility of booking the experts you need, when you need them."
      :ui="{
        background: 'dark:bg-gradient-to-b from-gray-700/50 to-gray-900/50',
        backgroundImage: 'url(/assets/for/2.png)',
        body: {
          base: 'flex-1',
          background: 'dark:bg-gray-900/50'
        }
      }"
    >
      <template #default>
        <div class="flex flex-col items-center justify-center">
          <UButton size="xl" color="white" icon="i-ph-plugs-connected-duotone" to="/training">
            Become a Partner
          </UButton>
        </div>
      </template>
    </ULandingCard>
  </UPageGrid>
</template>
