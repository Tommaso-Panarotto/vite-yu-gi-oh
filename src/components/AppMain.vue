<script>
import CardsCounter from "./CardsCounter.vue";
import SetList from "./SetList.vue";
import SetListCard from "./SetListCard.vue";

export default {
    data() {
        return {

        }
    },
    components: {
        CardsCounter,
        SetList,
        SetListCard
    }
}
</script>

<template>
    <CardsCounter />
    <SetList />
    <SetListCard />
</template>

<style lang="scss" scoped></style>