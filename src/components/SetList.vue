<script>
import SetListCard from "./SetListCard.vue";

export default {
    data() {
        return {

        }
    },
    components: {
        SetListCard
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
    <div class="row ">
        <SetListCard v-for="card in cardListStaf" :key="card.id" :cardObj="card" />
    </div>
</template>

<style lang="scss" scoped></style>