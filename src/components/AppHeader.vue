<template>
  <header>
      <input type="text" v-model= "inputUser" >
      <button @click="$emit('searchClick', inputUser)" >Search film</button>
  </header>
</template>

<script>

export default {
    name: "AppHeader",
    data: function() {
        return {
        inputUser: "",
        }
    },
}

</script>

<style lang="scss" scoped>

</style>