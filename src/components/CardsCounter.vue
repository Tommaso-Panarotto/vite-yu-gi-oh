<script>
import { store } from "../store.js";

export default {
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="counter px-3">Found {{ store.cardItems.length }} cards</div>
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