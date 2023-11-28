<template>
  <div class="bg-white">
    <div
      class="mx-auto grid max-w-7xl gap-x-8 gap-y-20 px-6 lg:px-8 xl:grid-cols-3"
    >
      <div class="max-w-2xl">
        <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
          {{ currentMessage }}
        </h2>
        <p class="mt-6 text-lg leading-8 text-gray-600">
          Rivolgetevi da noi per le vostre necessitá di piccoli e grandi lavori
        </p>
      </div>
      <ul
        role="list"
        class="grid gap-x-8 gap-y-6 sm:grid-cols-2 sm:gap-y-8 xl:col-span-2"
      >
        <li v-for="giorno in settimana" :key="giorno.giorno">
          <orario
            :giorno="giorno.giorno"
            :ora_apertura_mattina="giorno.apertura_mattina"
            :ora_chiusura_mattina="giorno.chiusura_mattina"
            :ora_apertura_pomeriggio="giorno.apertura_pomeriggio"
            :ora_chiusura_pomeriggio="giorno.chiusura_pomeriggio"
          />
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import orario from './orario.vue'
const currentMessage = ref('')
const settimana = [
  {
    day: 1,
    giorno: 'Lunedì',
    apertura_mattina: "9:00",
    chiusura_mattina: "12:00",
    apertura_pomeriggio: "15:00",
    chiusura_pomeriggio: "19:30",
  },
  {
    day: 2,
    giorno: 'Martedì',
    apertura_mattina: '8:30',
    chiusura_mattina: '12:30',
    apertura_pomeriggio: '15:00',
    chiusura_pomeriggio: '19:30',
  },
  {
    day: 3,
    giorno: 'Mercoledì',
    apertura_mattina: '8:30',
    chiusura_mattina: '12:30',
    apertura_pomeriggio: '15:00',
    chiusura_pomeriggio: '19:30',
  },
  {
    day: 4,
    giorno: 'Giovedì',
    apertura_mattina: '8:30',
    chiusura_mattina: '12:30',
    apertura_pomeriggio: '15:00',
    chiusura_pomeriggio: '19:30',
  },
  {
    day: 5,
    giorno: 'Venerdì',
    apertura_mattina: '8:30',
    chiusura_mattina: '12:30',
    apertura_pomeriggio: '15:00',
    chiusura_pomeriggio: '19:30',
  },
  {
    day: 6,
    giorno: 'Sabato',
    apertura_mattina: '8:30',
    chiusura_mattina: '12:30',
    apertura_pomeriggio: 'Chiuso',
    chiusura_pomeriggio: 'Chiuso',
  },
  {
    day: 0,
    giorno: 'Domenica',
    apertura_mattina: 'Chiuso',
    chiusura_mattina: 'Chiuso',
    apertura_pomeriggio: 'Chiuso',
    chiusura_pomeriggio: 'Chiuso',
  }
]

const getMessage = () => {
    const date = new Date()
    const day = date.getDay()
    const hour = date.getHours()
    const minutes = date.getMinutes()
    if (day > 0) {
        const giorno = settimana[day-1]
        if (hour >= 0 && hour < 15) {
            const apertura = giorno.apertura_mattina.split(':')
            const chiusura = giorno.chiusura_mattina.split(':')
            if (hour > parseInt(apertura[0]) && hour < parseInt(chiusura[0])) {
                return 'Siamo aperti! Ti aspettiamo!'
            }
            if ((hour == parseInt(apertura[0]) && minutes >= parseInt(apertura[1])) || 
                (hour == parseInt(chiusura[0]) && minutes <= parseInt(chiusura[1]))) {
                    return 'Siamo aperti! Ti aspettiamo!'
            }
            if (hour <= parseInt(apertura[0])) {
                return `Stiamo riposando... oggi apriamo alle ${giorno.apertura_mattina}, ti aspettiamo!`
            }
            if (day == 6) {
                return 'Oggi siamo chiusi. Lunedì siamo aperti dalle 9:00. Ti aspettiamo, Buon Sabato!'
            }
            return `Stiamo riposando... riapriremo alle ${giorno.apertura_pomeriggio}, ti aspettiamo!`
        } else {
            if (day == 6) {
                return 'Oggi siamo chiusi. Lunedì siamo aperti dalle 9:00. Ti aspettiamo, Buon Sabato!'
            }
            const apertura = giorno.apertura_pomeriggio.split(':')
            const chiusura = giorno.chiusura_pomeriggio.split(':')
            if (hour > parseInt(apertura[0]) && hour < parseInt(chiusura[0])) {
                return 'Siamo aperti! Ti aspettiamo!'
            }
            if ((hour == parseInt(apertura[0]) && minutes >= parseInt(apertura[1])) || 
                (hour == parseInt(chiusura[0]) && minutes <= parseInt(chiusura[1]))) {
                    return 'Siamo aperti! Ti aspettiamo!'
            }
            return `Siamo chiusi, domani ${settimana[day].giorno}, riapriremo alle ${giorno.apertura_mattina}. Buona serata.`
        }
    } else {
        return 'Oggi siamo chiusi. Lunedì siamo aperti dalle 9:00. Ti aspettiamo, Buona Domenica!'
    }
}

onMounted(() => {
  currentMessage.value = getMessage()
})
</script>
