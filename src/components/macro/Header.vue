<template>
    <header>
        <img src="../../assets/img/logo-netflix.png" alt="logo netflix">
        <SearchBar/>
    </header>
</template>

<script>
import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'Header',
    components: {
        SearchBar
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/partials/variables.scss';

    header {
        height: 70px;
        background-color: $backgroundColor;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 40px;
    }
</style>