<template>
    <div class="container">
       
        <div> {{ cardObj.original_title }}</div>
        <div> {{ cardObj.title }}</div>
        <div> {{ cardObj.original_language }}</div>
        <div> {{ cardObj.vote_average }}</div>
      
    </div>
</template>

<script>
export default {
    name: "AppCard",
    props: ["cardObj"],
}
</script>

<style lang="scss" scoped>

.container {
    border: 2px solid black;
    width: 100px;
    margin: 10px
}

</style>