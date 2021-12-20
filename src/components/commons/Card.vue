<template>
    <section>
        <li>
            <h3>{{film.title}}</h3>
            <p>{{film.original_title}}</p>
            <p>{{film.original_language}}</p>
            <p>{{film.vote_average}}</p>
        </li>
    </section>
</template>

<script>
import dataShared from '../../shared/dataShared';

export default {
    name: 'Card',
    data() {
        return {
            dataShared
        }
    }
}
</script>

<style lang="scss" scoped>

</style>