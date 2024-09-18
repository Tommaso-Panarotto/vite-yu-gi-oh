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
                    console.log(this.cardItems);
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
        <div class="col-3 gy-3" v-for="card in cardItems">
            <SetListCard />
        </div>
    </div>
</template>

<style lang="scss" scoped></style>