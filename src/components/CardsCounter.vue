<script>


export default {
    data() {
        return {

        }
    },
    props: {
        cardListStaf: {
            type: Array,
            required: true,
        }
    }
}
</script>

<template>
    <div class="counter px-3">Found {{ cardListStaf.length }} cards</div>
</template>

<style lang="scss" scoped>
.counter {
    height: 40px;
    background-color: #212429;
    color: white;
    line-height: 40px;
    font-weight: bolder;
}
</style>