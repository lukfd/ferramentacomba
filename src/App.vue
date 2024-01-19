<template>
  <div class="bg-white">
    <myheader />

    <div class="relative isolate px-6 pt-14 lg:px-8">
      <div class="mx-auto max-w-5xl py-16 sm:py-30 lg:py-56 z-50">
        <h1 class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">
          Qualità, Esperienza e Cortesia
        </h1>
        <h5 class="text-1xl tracking-tight text-gray-900 sm:text-2xl">
          al vostro servizio dal 1985
        </h5>
      </div>
      <div class="hidden md:flex absolute top-28 left-8" style="z-index: -2;">
        <img src="/chiavi1.jpg" class="rounded-md h-40" />
      </div>
      <div class="hidden md:flex absolute top-32 right-8" style="z-index: -2;">
        <img src="/chiavi2.jpg" class="rounded-md h-48 w-62" />
      </div>
      <div class="hidden md:flex absolute bottom-0 left-8" style="z-index: -2;">
        <img src="/interno.jpg" class="rounded-md h-48 w-62" />
      </div>
      <div class="hidden md:flex absolute top-40 right-40" style="z-index: -2;">
        <img src="/sait.jpg" class="rounded-md h-48 w-62" />
      </div>
      <div class="hidden md:flex absolute bottom-2 right-80 left-80" style="z-index: -2;">
        <img src="/wd40.jpg" class="rounded-md h-32 w-54" />
      </div>
      <div class="hidden md:flex absolute bottom-14 right-24" style="z-index: -2;">
        <img src="/avviso.svg" height="225rem" width="500rem" />
      </div>
    </div>

    <div class="relative isolate px-6 pt-14 lg:px-8" id="orari">
      <div class="mx-auto max-w-5xl py-2 sm:pt-16 sm:pb-30 lg:pt-10 lg:py-56">
        <orari />
      </div>
    </div>

    <div class="relative isolate px-6 pt-14 lg:px-8" id="dovesiamo">
      <div class="mx-auto max-w-5xl pt-2 sm:pt-2 sm:pb-30 lg:pt-2 lg:py-56">
        <dovesiamo />
      </div>
    </div>

    <div class="relative isolate px-6 pt-14 lg:px-8" id="chisiamo">
      <div class="mx-auto max-w-5xl py-2 sm:py-2 lg:py-56">
        <chisiamo />
      </div>
    </div>
  </div>
</template>

<script setup>
import myheader from './components/header.vue'
import orari from './components/orari.vue'
import dovesiamo from './components/dovesiamo.vue'
import chisiamo from './components/chisiamo.vue'
</script>
