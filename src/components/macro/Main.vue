<template>
    <main>
        <Movies/>
        <TvSeries/>
    </main>
</template>

<script>
import Movies from '../sections/Movies.vue';
import TvSeries from '../sections/TvSeries.vue';


export default {
    name: 'Main',
    components: {
        Movies,
        TvSeries
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/partials/variables.scss';

    main {
        background-color: $backgroundColor;
    }
</style>