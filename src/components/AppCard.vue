<template>
    <div class="container">
       
        <div> {{ movie.title }} </div>
        <div> {{ movie.original_title }} </div>
        <div> {{ movie.original_language }} </div>
        <div> {{ movie.vote_average }} </div>
        
      
    </div>
</template>

<script>
export default {
    name: "AppCard",
    props: {
        movie: Object
    },
}
</script>

<style lang="scss" scoped>

.container {
    border: 2px solid black;
    width: 100px;
    margin: 10px
}

</style>