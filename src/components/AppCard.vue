<script>
import { store } from '../store';
import axios from "axios";



export default {
    name: "AppCard",
    props: ['card'],
    data() {
        return {
            store
        };
    }
};

</script>

<template>
    <div class="card">
        <div class="card__side card__side--front">
            <img :src="'https://image.tmdb.org/t/p/w500' + card.poster_path" alt="Image">
        </div>
        <div class="card__side card__side--back">
            <h2>{{ card.title }}</h2>
            <h3>{{ card.original_title }}</h3>
            <p> Vote: {{ card.vote_average }}</p>
            <p>{{ card.overview }}</p>
        </div>
    </div>
</template>


<style lang="scss" scoped>
@use '../components/style/partials/variables' as *;
@use '../components/style/partials/mixins.scss' as *;
@use "../components/style/general.scss";


.card {
    height: 15rem;
    width: 12rem;
    margin: 0.5rem;
    perspective: 1500px;

    .card__side {
        position: absolute;
        width: 100%;
        height: 100%;
        backface-visibility: hidden;
        transition: transform 0.6s ease;

        img {
            height: 100%;
            width: 100%;
            object-fit: contain;
        }
    }


    .card__side--front {
        // background: #fff;
    }

    .card__side--back {
        transform: rotateY(180deg);
        background: $primary;
        color: #fff;
        overflow: auto;

    }

    &.card:hover .card__side--front {
        transform: rotateY(180deg);
    }

    &.card:hover .card__side--back {
        transform: rotateY(0);
    }
}
</style>