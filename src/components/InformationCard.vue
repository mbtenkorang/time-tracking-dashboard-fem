<script setup>

const props = defineProps({
    cardTitle: {
        type: String,
        required: true
    },
    currentTimeValue: {
        type: Number,
        required: true
    },
    previousTimeValue: {
        type: Number,
        required: true
    },
    selectedTime: {
        type: String
    }
})

</script>

<template>
    <section class="information--container" :class="cardTitle.toLowerCase()">
        <div class="information--card">
            <div class="information--title">
                <h2>
                    {{ cardTitle }}
                </h2>
                <span>...</span>
            </div>
            <div class="card--details">
                <p class="current--value">{{ currentTimeValue }}
                    {{ currentTimeValue > 1 || currentTimeValue === 0 ?
                    'hrs' :
                    'hr' }}
                </p>
                <p v-if="selectedTime==='daily'" class="previous--value">Yesterday - {{ previousTimeValue }}
                    {{previousTimeValue > 1 || previousTimeValue === 0 ? "hrs" : 'hr' }}
                </p>
                <p v-else-if="selectedTime === 'weekly'" class="previous--value">Last Week - {{ previousTimeValue}}
                    {{previousTimeValue > 1 || previousTimeValue === 0 ? "hrs" : 'hr' }}
                </p>
                <p v-else class="previous--value">Last Month - {{ previousTimeValue }}
                    {{previousTimeValue > 1 || previousTimeValue === 0 ? "hrs" : 'hr' }}
                </p>
            </div>
        </div>
    </section>
</template>
