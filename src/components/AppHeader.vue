<template>
  <header class="header">
      <div class="image-logo">
        <img src="../assets/img/alexlogo.png" alt="">
      </div>
      <div class="search">
        <input type="text" v-model= "inputUser" >
        <button @click="$emit('searchClick', inputUser)" >Search film</button>
      </div>
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

.header {
    background-color: rgb(68, 65, 64);
    display: flex;
    justify-content: space-around;
    height: 80px;
    line-height: 80px;
}

.search {
    margin-left: 20px;

    input {
        height: 30px;
        width: 100px;
        background-color:rgb(68, 65, 64);
        color: white;
        border: none;
        border-bottom: 1px solid grey;
        margin-right: 10px;
    }

    input:focus {
        outline: none;
    }

    button {
        height: 30px;
        padding: 5px;
        color: white;
        background-color:rgb(68, 65, 64); 
        border: none;
        border-bottom: 1px solid rgb(219, 32, 44);
    }
}


</style>