<template>
    <section>
        <!-- lista serie tv ricerca utente -->
        <div v-if="dataShared.searchValue">
            <h2>Lista serie TV</h2>
            <vue-horizontal>
            <ul class="movies-list">
                <Card v-for="(tvSerie,index) in dataShared.tvSeries " :key="index" :card="tvSerie"/>
            </ul>
            </vue-horizontal>
        </div>
        <!-- /lista serie tv ricerca utente -->

        <!-- lista serie tv popolari -->
        <div v-else>
            <h2>Serie TV del momento</h2>
            <vue-horizontal>
            <ul class="movies-list">
                <Card v-for="(tvSerie,index) in dataShared.popularTvSeries " :key="index" :card="tvSerie"/>
            </ul>
            </vue-horizontal>
        </div>
        <!-- /lista serie tv popolari -->
    </section>
</template>


<script>
import dataShared from '../../shared/dataShared';
import Card from '../commons/Card.vue';

export default {
    name: 'TvSeries',
    components: {
        Card
    },
    data() {
        return {
            dataShared
        }
    }
}
</script>


<style lang="scss" scoped>
    section {
        padding: 20px 30px;

        .movies-list {
            display: flex;

            >* {
                width: calc(100% / 5 - 10px);
                margin: 5px;
            }
        }
    }
</style>