<template>
    <li class="card-information">
        <div>
            <span>Titolo:</span>
            <h3>{{movie.title}}</h3>
        </div>
        <div>
            <span>Titolo originale:</span>
            <h3>{{movie.original_title}}</h3>
        </div>
        <div>
            <span>Lingua:</span>
            <h3>{{movie.original_language}} <country-flag :country="movie.original_language == 'en' ? 'gb' : movie.original_language " size='small' class="flag"/></h3>
        </div>
        <div>
            <span>Voto:</span>
            <h3>{{movie.vote_average}}</h3>
        </div>
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

.card-information {
    border: 1px solid black;

    div {
        margin-bottom: 8px;

        .flag {
        position: relative;
        bottom: 3px;
        left: 5px;
        }
    }
}
</style>