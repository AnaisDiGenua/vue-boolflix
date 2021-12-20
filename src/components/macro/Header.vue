<template>
    <header>
        <img src="../../assets/img/logo-netflix.png" alt="logo netflix">
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/partials/variables.scss';

    header {
        height: 70px;
        background-color: $backgroundColor;
        display: flex;
        align-items: center;
    }
</style>