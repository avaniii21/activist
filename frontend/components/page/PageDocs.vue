<template>
  <div
    class="responsive-py-4 responsive-px-5 flex w-full flex-col items-center bg-light-layer-0 text-light-text dark:bg-dark-layer-0 dark:text-dark-text"
  >
    <div class="flex w-11/12 items-start pb-2 sm:w-10/12 md:w-full">
      <PageBreadcrumbs v-if="!aboveMediumBP" />
    </div>
    <PageContent
      :imgURL="imgURL"
      :imgAltText="imgAltText"
      :includeBreadcrumbs="true"
    >
      <slot />
    </PageContent>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  imgURL: string;
  imgAltText: string;
}>();

const aboveMediumBP = useBreakpoint("md");
</script>
