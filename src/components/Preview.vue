<template>


<ul>
    <li v-for="gift in gifts">
        <img :src="gift.images.fixed_height.url" alt="">
    </li>
</ul>


</template>

<script>
export default {
    props:['gifts'],





}
</script>

<style scoped>
ul{

}
li{
    list-style: none;
    float: left;
    margin:20px;
    
}

</style>