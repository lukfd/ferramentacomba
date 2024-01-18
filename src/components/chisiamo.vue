<template>
  <div class="bg-white">
    <div class="mx-auto grid max-w-7xl gap-x-8 px-6 lg:px-8 xl:grid-cols-2">
      <div class="max-w-2xl">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
          Chi siamo
        </h2>
        <p class="mt-6 text-lg leading-8 text-gray-600">
          Ferramenta Comba inizia la sua attività di vendita al minuto di
          ferramenta nell'agosto del 1985 per iniziativa di Albino e Marco Comba
          con l'aiuto di papà Angelo. Dall'inizio a oggi l'azienda cresce per
          soddisfare le esigenze della propria clientela ampliando continuamente
          la sua gamma di articoli di ferramenta spaziando anche in altri
          settori.
        </p>
      </div>
      <div class="flex">
            <img src="/people/angelo.png" alt="">
        </div>
    </div>
    <div class="flex py-12">
        <ul
          role="list"
          class="grid gap-x-12 gap-y-6 sm:grid-cols-3 sm:gap-y-12 xl:col-span-3"
        >
          <li v-for="person in people" :key="person.name">
            <div class="flex items-center gap-x-2">
              <img
                class="h-20 w-20 rounded-full"
                style="object-fit: cover"
                :src="person.imageUrl"
                alt=""
              />
              <div>
                <h3
                  class="text-base font-semibold leading-7 tracking-tight text-gray-900"
                >
                  {{ person.name }}
                </h3>
                <p class="text-sm font-semibold leading-6 text-indigo-600">
                  {{ person.role }}
                </p>
              </div>
            </div>
          </li>
        </ul>
    </div>
  </div>
</template>

<script setup>
const people = [
  {
    name: 'Angelo Comba',
    imageUrl: '/people/angelo2.png',
  },
  {
    name: 'Albino Comba',
    imageUrl: '/people/albino2.png',
  },
  {
    name: 'Marco Comba',
    imageUrl: '/people/marco.png',
  }
]
</script>
