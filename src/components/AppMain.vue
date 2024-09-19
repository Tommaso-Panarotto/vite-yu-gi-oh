<script>
import CardsCounter from "./CardsCounter.vue";
import SetList from "./SetList.vue";
import LoaderMain from "./LoaderMain.vue";
import CardsArchetypesSelect from "./CardsArchetypesSelect.vue";
import axios from 'axios';

export default {
    data() {
        return {
            APIUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?",
            loading: true,
            cardItems: []
        }
    },
    components: {
        CardsCounter,
        SetList,
        LoaderMain,
        CardsArchetypesSelect
    },
    methods: {
        getCards(query = "Blue-Eyes") {
            axios.get(this.APIUrl, {
                params: {
                    archetype: query
                }
            })
                .then((response) => {
                    this.cardItems = response.data.data;
                })
                .finally(() => {
                    this.loading = false
                })
        },
        selectArchetype(message) {
            console.log(message);
            this.getCards(message);
        }
    },
    created() {
        setTimeout(this.getCards, 2000);
    }
}
</script>

<template>
    <CardsArchetypesSelect @select="selectArchetype" />
    <LoaderMain v-if="loading" />
    <main class="container" v-else>
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