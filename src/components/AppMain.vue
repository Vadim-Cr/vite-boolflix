<script>
import { store } from '../store';
import axios from "axios";
import AppCard from './AppCard.vue';

export default {
    name: "AppMain",
    components: {
        AppCard
    },
    data() {
        return {
            store
        };
    },
    created() {
        let myUrl = store.apiURL; // replace with your actual URL

        axios.get(myUrl)
            .then(result => {
                this.store.movieList = result.data.results
                this.store.loading = false;
            })
            .catch(err => {
                console.log(err);
            })
    }
};
</script>

<template>
    <div class="container">
        <AppCard v-for="(card, index) in store.movieList" :key="index" :card="card" />
    </div>
</template>

<style lang="scss" scoped>
@use '../components/style/partials/variables' as *;
@use '../components/style/partials/mixins.scss' as *;
@use "../components/style/general.scss";

.container {
    min-height: 20rem;
    background-color: $tertiary;
    padding: 2rem;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
}
</style>
