<template>
    <!-- inizio card box -->
    <li class="card-box">
        <!-- immagine card -->
        <div v-if="card.poster_path == null" class="card-img">
            <img src="../../assets/img/image-not-found.jpeg" alt="card.title || card.name">
        </div>
        <div v-else class="card-img">
            <img :src="`https://image.tmdb.org/t/p/w342/${card.poster_path}`" :alt="card.title || card.name">
        </div>
        <!-- /immagine card -->
        <!-- informazioni card -->
        <div class="card-information">
            <div class="card-title">
                <h3>{{card.title || card.name}}</h3>
            </div>
            <div class="language">
                <span>lingua: <country-flag :country="changeFlag(card.original_language)" size='small' class="flag"/></span>
            </div>
            <div class="vote">
                <span>Voto:</span>
                <span class="star" v-for="vote in changeVote" :key="vote.id"><i class="fas fa-star"></i></span>
                <span class="star" v-for="vote in (5 - changeVote)" :key="vote.id"><i class="far fa-star"></i></span>
            </div>
            <div class="overview">
                <div v-if="card.overview">
                    <span class="overview-text">{{card.overview}}</span>
                </div>
                <div v-else></div>
            </div>
        </div>
        <!-- /informazioni card -->
    </li>
    <!-- /card-box -->
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
    },
    computed: {
        changeVote() {
            return Math.ceil(this.card.vote_average / 2)
        }
    }
}
</script>

<style lang="scss" scoped>

.card-box {
    border: 1px solid black;
    position: relative;

    &:hover img {
        filter: blur(0.5);
        filter: brightness(0.2);
    }

    &:hover .card-information {
        display: block;
        color: white;
    }

    .card-img  {
        height: 400px;

        img {
            width: 100%;
            height: 100%;
        }
    }
}


.card-information {
    position: absolute;
    top: 20px;
    left: 15px;
    right: 15px;
    display: none;

    .card-title  {
        margin-bottom: 50px;
        h3 {
            font-size: 1.25rem;
            text-transform: uppercase;
            text-align: center;
        }
    }

    .vote .star{
        color: yellow;
    }

    .overview {
        height: 220px;
        overflow-y: auto;
    }
    .overview .overview-text {
        font-size: .9375rem;
    }

    div {
        margin-bottom: 8px;
    }
}

</style>