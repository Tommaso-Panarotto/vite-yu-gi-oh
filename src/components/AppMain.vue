<script>
import CardsCounter from "./CardsCounter.vue";
import SetList from "./SetList.vue";
import LoaderMain from "./LoaderMain.vue";

export default {
    data() {
        return {
            loading: true,
        }
    },
    components: {
        CardsCounter,
        SetList,
        LoaderMain
    }
}
</script>

<template>
    <main class="container">
        <LoaderMain />
    </main>
    <main class="container">
        <CardsCounter />
        <SetList />
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: white;
    margin-top: 50px;
    padding: 30px;
    min-height: 500px;
}
</style>