<template>
    <section>
        <div class="search-bar">
            <input type="text" placeholder="cerca film">
            <span><i class="fas fa-search"></i></span>
        </div>
    </section>
</template>

<script>
export default {
    name: 'SearchBar'
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/partials/variables.scss';
    input {
        padding: 5px 15px;
        border-radius: 0.5rem;
        margin-right: 10px;
    }

    span {
        color: $white;
        font-size: 1.125rem;
        vertical-align: middle;
    }

</style>