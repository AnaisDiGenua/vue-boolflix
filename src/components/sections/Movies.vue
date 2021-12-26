<template>
    <section>
        <!-- lista film ricerca utente-->
        <div v-if="dataShared.searchValue">
            <h2>Lista film</h2>
            <ul class="movies-list">
                <Card v-for="(movie,index) in dataShared.movies " :key="index" :card="movie"/>
            </ul>
        </div>
        <!-- /lista film ricerca utente -->

        <!-- lista film popolari -->
        <div v-else>
            <h2>Film del momento</h2>
            <ul class="movies-list">
                <Card v-for="(movie,index) in dataShared.popularMovies " :key="index" :card="movie"/>
            </ul>
        </div>
        <!-- /lista film popolari -->
    </section>
</template>


<script>
import dataShared from '../../shared/dataShared';
import Card from '../commons/Card.vue';

export default {
    name: 'Movies',
    components: {
        Card
    },
    data() {
        return {
            dataShared,
        }
    }
}
</script>


<style lang="scss" scoped>
    section {
        padding: 20px 30px;

        .movies-list {
            display: flex;
            flex-wrap: wrap;

            >* {
                width: calc(100% / 5 - 20px);
                margin: 10px;
            }
        }
    }
</style>