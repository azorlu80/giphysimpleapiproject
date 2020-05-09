<template>
<div class="search">
    <input @keypress.enter="handleSearch" v-model="query" type="text">
    <button @click="handleSearch">Search</button>
</div>    
</template>

<script>
export default {
  data(){
      return{
          query:'',

      }
  },

    methods:{
        handleSearch(){
            this.$emit("queryRequested",this.query)
        }
    }
    
}
</script>

<style scoped>

.search input {
    padding:10px 20px;
    border:1px solid #ccc;
    border-radius:5px;
    width: 400px;

}
.search button{
    padding: 5px 15px;
    border: 1px solid #ccc;
    background-color:#a4ddf4;
    color: #FFF;
    font-size: 16px;
    border-radius: 5px;



}
</style>
