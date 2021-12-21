<template>
    <section>
        <h2>Lista serie TV</h2>
        <ul class="movies-list">
            <Card v-for="(tvSerie,index) in dataShared.tvSeries " :key="index" :card="tvSerie"/>
        </ul>
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
            flex-wrap: wrap;

            >* {
                width: calc(100% / 5 - 20px);
                margin: 10px;
            }
        }
    }
</style>