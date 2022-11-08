<template>
    <p >Reaction Time: {{score}}ms</p>
    <p class="font-bold text-green-500">{{rank}}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "to the moon"
        }
        else if (this.score < 450) {
            this.rank = "thumbs up"
        }
        else {
            this.rank = "tortoise speed"
        }
        }
    }
</script>