<script>
import SetListCard from "./SetListCard.vue";
import axios from 'axios';

export default {
    data() {
        return {
            cardItems: [],
            APIUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0"
        }
    },
    components: {
        SetListCard
    },
    methods: {
        getCards() {
            axios.get(this.APIUrl)
                .then((response) => {
                    this.cardItems = response.data.data;
                    console.table(this.cardItems);
                    console.log(response.data.data);
                    console.log(response.data.data[0].card_images[0].image_url);
                    console.log(response.data.data[0].name);
                    console.log(response.data.data[0].race);
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
        <SetListCard v-for="card in cardItems" :key="card.id" :cardObj="card" />
    </div>
</template>

<style lang="scss" scoped></style>