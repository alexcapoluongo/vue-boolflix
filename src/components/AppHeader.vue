<template>
  <header>
      <input type="text" v-model= "inputUser" >
      <button @click="modifyAxios" >Search film</button>
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
    methods: {
        
        modifyAxios: function() {
            this.movieSearched = this.inputUser
            console.log(this.movieSearched);
            this.inputUser="";
         
        }

    }
}

</script>

<style>

</style>