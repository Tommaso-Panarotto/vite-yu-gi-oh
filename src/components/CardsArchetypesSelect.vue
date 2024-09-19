<script>
import axios from 'axios';

export default {
    data() {
        return {
            APIUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
            archetypesList: [],
            archetypeName: "",
        }
    },
    methods: {
        getArchetypes() {
            axios.get(this.APIUrl)
                .then((response) => {
                    this.archetypesList = response.data;
                })
        },
        getArchetypeName(result) {
            console.log(result)
        }
    },
    created() {
        this.getArchetypes()
    }
}
</script>

<template>
    <div class="select container mt-5">
        <select class="form-select" aria-label="Default select example" v-model="archetypeName"
            @click="getArchetypeName(archetypeName)">
            <option selected>Select a Archetypes</option>
            <option :value="archetype.archetype_name" v-for="archetype of archetypesList">{{
                archetype.archetype_name }}
            </option>
        </select>
    </div>
</template>

<style lang="scss" scoped></style>