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
    <main class="container">
        <CardsCounter />
        <SetList />
        <SetListCard />
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: white;
    margin-top: 50px;
    padding: 30px;
}
</style>