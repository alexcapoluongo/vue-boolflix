<template>

    <div class="movie-list">
            <AppCard v-for="item in movies" :key="item.id" :movie="item"/>
            
    </div>
</template>

<script>

import AppCard from "./AppCard.vue"

export default {
    name: "MovieList",

    components: {
        AppCard,
    },

    props: {
        movies: Array
    }

}
</script>

<style lang="scss" scoped>

.movie-list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

</style>