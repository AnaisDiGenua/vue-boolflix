<template>
    <section>
        <ul>
            <li v-for="(film,index) in dataShared.films " :key="index">
                <h3>{{film.title}}</h3>
                <p>{{film.original_title}}</p>
                <p>{{film.original_language}}</p>
                <p>{{film.vote_average}}</p>
                <!-- <Card/> -->
            </li>
        </ul>
    </section>
</template>

<script>
import dataShared from '../../shared/dataShared';
// import Card from '../commons/Card.vue';

export default {
    name: 'Films',
    components: {
        // Card
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