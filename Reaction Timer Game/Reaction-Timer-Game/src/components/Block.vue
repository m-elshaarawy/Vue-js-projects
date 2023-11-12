<template>

<div class="block" v-if="showblock" @click="stopTimer">
    Cick Me ...
</div>

</template>
<script>
export default {
    props:['delay'],
    data() {
        return {
            showblock: false,
            timer: null,
            reactionTime: 0,
        }
    },
    mounted(){
        setTimeout(() => {
            this.showblock = true;
            this.startTimer();
        } , this.delay)
    },
    methods: {
        startTimer(){
            this.timer = setInterval(() => {
                this.reactionTime += 10;
            }, 10)
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit('end',this.reactionTime);
        }
    }
}
</script>

<style scoped>

.block {
    width: 400px;
    border-radius: 20px;
    background-color: mediumpurple;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    font-weight: 500;
}

</style>