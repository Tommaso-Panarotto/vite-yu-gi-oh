<script>
import SetListCard from "./SetListCard.vue";

export default {
    data() {
        return {

        }
    },
    components: {
        SetListCard
    }
}
</script>

<template>
    <div class="row ">
        <div class="col-3 gy-3" v-for="n in 20">
            <SetListCard />
        </div>
    </div>
</template>

<style lang="scss" scoped></style>