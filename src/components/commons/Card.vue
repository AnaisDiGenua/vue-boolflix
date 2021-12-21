<template>
    <li class="card-information">
        <h3>{{movie.title}}</h3>
        <p>{{movie.original_title}}</p>
        <p>{{movie.original_language}}</p>
        <p>{{movie.vote_average}}</p>
    </li>
</template>

<script>

export default {
    name: 'Card',
    props: {
        movie: Object
    }
}
</script>

<style lang="scss" scoped>

</style>