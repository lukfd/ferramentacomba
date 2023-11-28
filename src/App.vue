<template>
  <div class="bg-white">
    
    <myheader />

    <div class="relative isolate px-6 pt-14 lg:px-8">
      <div class="mx-auto max-w-5xl py-16 sm:py-30 lg:py-56">
        <h1 class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">
          Qualità, Esperienza e Cortesia
        </h1>
        <h5 class="text-1xl tracking-tight text-gray-900 sm:text-2xl">
          al vostro servizio dal 1985
        </h5>
      </div>
    </div>

    <div class="relative isolate px-6 pt-14 lg:px-8" id="orari">
      <div class="mx-auto max-w-5xl py-16 sm:pt-16 sm:pb-30 lg:pt-10 lg:py-56">
        <orari />
      </div>
    </div>

    <div class="relative isolate px-6 pt-14 lg:px-8" id="dovesiamo">
      <div class="mx-auto max-w-5xl pt-2 pb-16 sm:pt-2 sm:pb-30 lg:pt-2 lg:py-56">
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
