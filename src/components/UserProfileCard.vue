<script setup>
import avatarImage from "../assets/images/image-jeremy.png"
const emit = defineEmits(['getrecordforperiod'])

const handleSelectedTime = (event) => {
    emit('getrecordforperiod', event.target.innerHTML.toLowerCase())
}
</script>

<template>
    <div class="header--container">
        <header class="profile">
            <img :src="avatarImage" alt="Picture of Jeremy Robson">
            <h1>
                <span role="heading" aria-label="heading" aria-labelledby="heading" class="intro">Report for </span>
                <span role="heading" aria-label="heading" aria-labelledby="heading" class="name">Jeremy Robson</span>
            </h1>
        </header>
        <nav>
            <a @click.prevent="handleSelectedTime" href="daily">Daily</a>
            <a @click.prevent="handleSelectedTime" href="weekly">Weekly</a>
            <a @click.prevent="handleSelectedTime" href="monthly">Monthly</a>
        </nav>
    </div>

</template>