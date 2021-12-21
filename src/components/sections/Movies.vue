<template>
    <section>
        <ul>
            <Card v-for="(movie,index) in dataShared.movies " :key="index" :movie="movie"/>
        </ul>
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
            dataShared
        }
    }
}
</script>


<style lang="scss" scoped>
    section {
        padding: 20px 30px;

        li {
            margin-bottom: 20px;
        }
    }
</style>