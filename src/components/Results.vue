<template>
    <div class="block" >
        <h1>Results</h1>
        <h3>Reaction Time : {{ score }} ms</h3>
        <h3>Rank : {{ rank }}</h3>
    </div>
</template>

<script>
export default {
    props: {
        score: Number
    },
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if(this.score < 250){
            this.rank = 'Ninja fingers'
        } else if(this.score < 350){
            this.rank = 'Speedy Gonzalez'
        } else if (this.score < 500) {
            this.rank = 'rapid reflexes....'
        } else if (this.score < 700) {
            this.rank = 'You are slow'
        } else {
            this.rank = 'Snail Pace'
        }
    }
}
</script>

<style scoped>
    .block {
        background: rgb(194, 162, 169);
        color: rgb(0, 0, 0);     
    }
</style>