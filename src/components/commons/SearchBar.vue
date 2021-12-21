<template>
    <section>
        <div class="search-bar">
            <input v-model="dataShared.searchValue" type="text" placeholder="cerca film" @keyup.enter="search">
            <span @click="search"><i class="fas fa-search"></i></span>
        </div>
    </section>
</template>


<script>
import dataShared from '../../shared/dataShared';
import axios from 'axios';


export default {
    name: 'SearchBar',
    data() {
        return {
            dataShared
        }
    },
    methods: {
        search() {
                // chiamata movies
                axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                api_key: '254a592ae829f84f680ef45c8f4ae5be',
                query: dataShared.searchValue,
                language: 'it-IT'
                }
            })
            .then((response) => {
                this.dataShared.movies = response.data.results;
                console.log(response.data.results);
            })
            .catch(function (error) {
                console.log(error);
            }); 

                // chiamata serie tv
                axios.get('https://api.themoviedb.org/3/search/tv', {
                params: {
                api_key: '254a592ae829f84f680ef45c8f4ae5be',
                query: dataShared.searchValue,
                language: 'it-IT'
                }
            })
            .then((response) => {
                this.dataShared.tvSeries = response.data.results;
                console.log(response.data.results);
            })
            .catch(function (error) {
                console.log(error);
            }); 
        }
    }
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