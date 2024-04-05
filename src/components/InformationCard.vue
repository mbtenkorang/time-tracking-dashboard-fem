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
    }
})
</script>

<template>
    <section class="information--card">
        <div class="information--details">
            <h2>
                {{ cardTitle }}
                <span>...</span>
            </h2>
        </div>
        <div class="card--details">
            <p class="current--value">{{ currentTimeValue }}</p>
            <p class="previous--value">Last week - {{ previousTimeValue }}</p>
        </div>
    </section>
</template>