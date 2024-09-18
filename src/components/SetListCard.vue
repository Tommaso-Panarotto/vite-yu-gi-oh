<script>
export default {
    data() {
        return {

        }
    },
    props: {
        cardObj: {
            type: Object,
            required: true,
        }
    }
}
</script>

<template>
    <div class="col-3 gy-3">
        <div class="card">
            <img :src="cardObj.card_images[0].image_url" class="card-img-top" :alt="cardObj.name">
            <div class="card-body">
                <h4 class="card-text text-white">{{ cardObj.name }}</h4>
                <p class="card-text">{{ cardObj.race }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.card {
    border: 0;
    border-radius: 0;
    background-color: #D48F3B;
    text-align: center;

    h4 {
        height: 90px;
    }
}
</style>