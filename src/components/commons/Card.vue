<template>
    <li class="card-information">
        <div v-if="card.poster_path == null" class="card-img">
            <img src="../../assets/img/image-not-found.jpeg" alt="">
        </div>
        <div v-else class="card-img">
            <img :src="`https://image.tmdb.org/t/p/w342/${card.poster_path}`" alt="">
        </div>
        <div class="card-title">
            <span>Titolo:</span>
            <h3>{{card.title || card.name}}</h3>
        </div>
        <div class="card-original-title">
            <span>Titolo originale:</span>
            <h3>{{card.original_title || card.original_name}}</h3>
        </div>
        <div class="language">
            <span>Lingua:</span>
            <h3>{{card.original_language}} <country-flag :country="changeFlag(card.original_language)" size='small' class="flag"/></h3>
        </div>
        <div class="vote">
            <span>Voto:</span>
            <h3>{{card.vote_average}}</h3>
        </div>
    </li>
</template>

<script>

export default {
    name: 'Card',
    props: {
        card: Object
    },
    methods: {
        changeFlag(language) {
            if(language == 'en') {
                return 'gb'; 
            } else if (language == 'ja') {
                return 'jp';
            } else {
                return language;
            }
        }
    }
}
</script>

<style lang="scss" scoped>

.card-information {
    border: 1px solid black;

    div {
        margin-bottom: 8px;
    }

    .language .flag {
        position: relative;
        bottom: 3px;
        left: 5px;
    }

    .card-img img {
        width: 100%;
    }
}
</style>