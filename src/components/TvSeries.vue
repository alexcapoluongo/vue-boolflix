<template>

    <div class="movie-list">
            <TvSeriesCard v-for="item in tvseries" :key="item.id" :tvseries="item"/>
            
    </div>
</template>

<script>

import TvSeriesCard from "./TvSeriesCard.vue"

export default {
    name: "TvSeries",

    components: {
        TvSeriesCard,
    },

    props: {
        tvseries: Array
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