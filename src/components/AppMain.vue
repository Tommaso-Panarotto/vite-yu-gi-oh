<script>
import CardsCounter from "./CardsCounter.vue";
import SetList from "./SetList.vue";
import LoaderMain from "./LoaderMain.vue";
import axios from 'axios';

export default {
    data() {
        return {
            APIUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=37&offset=0",
            loading: true,
            cardItems: []
        }
    },
    components: {
        CardsCounter,
        SetList,
        LoaderMain
    },
    methods: {
        getCards() {
            axios.get(this.APIUrl)
                .then((response) => {
                    this.cardItems = response.data.data;
                }
                )
        }
    },
    mounted() {
        this.getCards();
    }
}
</script>

<template>
    <div class="container">
        <LoaderMain />
    </div>
    <main class="container">
        <CardsCounter :cardListStaf="cardItems" />
        <SetList :cardListStaf="cardItems" />
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