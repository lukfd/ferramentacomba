<template>
<div class="flex items-center">
    <div>
        <h3 class="text-base font-semibold leading-7 tracking-tight text-gray-900">
            {{ giorno }}
        </h3>
        <div class="flex flex-row">
            <p class="flex text-sm font-semibold leading-6">
                <div :style="ora_apertura_mattina == 'Chiuso' ? { color: 'red'} : {color: '#2c3196'}" >
                    {{ ora_apertura_mattina }}
                </div>
                <div 
                    :style="ora_chiusura_mattina == 'Chiuso' ? { color: 'red'} : {color: '#2c3196'}"
                    v-if="ora_apertura_mattina !== 'Chiuso' && ora_chiusura_mattina !== 'Chiuso'"
                >
                    -{{ ora_chiusura_mattina }}
                </div>
            </p>
        </div>
        <div class="flex flex-row">
            <p class="flex text-sm font-semibold leading-6">
                <div 
                    :style="ora_apertura_pomeriggio == 'Chiuso' ? { color: 'red'} : {color: '#2c3196'}"
                    v-if="ora_apertura_pomeriggio !== 'Chiuso' && ora_chiusura_pomeriggio !== 'Chiuso' || giorno !== 'Domenica'"
                >
                    {{ ora_apertura_pomeriggio }}
                </div>
                <div 
                    :style="ora_chiusura_pomeriggio == 'Chiuso' ? { color: 'red'} : {color: '#2c3196'}"
                    v-if="ora_apertura_pomeriggio !== 'Chiuso' && ora_chiusura_pomeriggio !== 'Chiuso'"
                >
                    -{{ ora_chiusura_pomeriggio }}
                </div>
            </p>
        </div>
    </div>
</div>
</template>

<script setup>
const props = defineProps({
    giorno: String, 
    ora_apertura_mattina: String,
    ora_chiusura_mattina: String,
    ora_apertura_pomeriggio: String,
    ora_chiusura_pomeriggio: String
})
</script>