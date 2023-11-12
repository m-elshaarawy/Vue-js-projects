<script>
export default {
props:['score'],
data() {
    return {
        rank: null,
    }
},
mounted(){
    if (this.score <= 250)
        this.rank = 'Shadow Warrior Fingers ^_^'
    else if (this.score <= 400)
        this.rank = 'Rapid Reflexes'
    else
        this.rank = 'Snail Pace ...'
}

}
</script>

<template>
    <p> reaction time : {{ score }} ms</p>
    <p class="rank"> {{ rank }} </p>
</template>


<style scoped>
.rank {
    font-size: 1.5em;
    color: crimson;
    font-weight: bold;
}
</style>