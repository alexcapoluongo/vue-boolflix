<template>
    <div class="container">
        <p> {{ cardObj }} </p>
        <p> {{ cardObj }} </p>
        <p> Stars </p>
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
}

</style>