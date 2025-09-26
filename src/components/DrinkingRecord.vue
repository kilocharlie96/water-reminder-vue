<template>
    <saved-record>
        <h1>{{ waterAmount }} L</h1>
        <p>Stav vypitej vody pred záznamom: {{ litresTotalDay }} L</p>
        <p>Stav vypitej vody vrátane záznamu: {{ litresTotalNow }} L</p>
        <p>Čas: {{ time }}</p>
        <p>{{ remainingToTarget }}</p>
    </saved-record>
</template>

<script>
    export default {
        props: {
            waterAmount: {
                type: Number,
            },
            litresTotalNow: {
                type: Number,
            },
            litresTotalDay: {
                type: Number
            },
            time: {
                type: Number,
            },
            remainingToTarget: {
                type: Number,
            }
        }
    }
</script>