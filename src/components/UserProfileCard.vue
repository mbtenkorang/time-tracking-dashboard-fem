<script setup>

const emit = defineEmits(['handleClick'])

const handleClick = (event) => {
    emit('handleClick', event.target.innerHTML.toLowerCase())
}
</script>

<template>
    <div>
        <header class="card">
            <div>
                <img src="" alt="">
                <h1>
                    <span>Report for </span>
                    <span>Jeremy Robson</span>
                </h1>
            </div>
        </header>
        <nav>
            <a @click.prevent="handleClick" href="daily">Daily</a>
            <a @click.prevent="handleClick" href="weekly">Weekly</a>
            <a @click.prevent="handleClick" href="monthly">Monthly</a>
        </nav>
    </div>

</template>