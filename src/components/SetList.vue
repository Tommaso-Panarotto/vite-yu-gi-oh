<script>
import SetListCard from "./SetListCard.vue";
import axios from 'axios';
import { store } from "../store.js";

export default {
    data() {
        return {
            store,
            APIUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0"
        }
    },
    components: {
        SetListCard
    },
    methods: {
        getCards() {
            axios.get(this.APIUrl)
                .then((response) => {
                    this.store.cardItems = response.data.data;
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
    <div class="row ">
        <SetListCard v-for="card in store.cardItems" :key="card.id" :cardObj="card" />
    </div>
</template>

<style lang="scss" scoped></style>