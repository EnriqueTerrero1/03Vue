<template>
  <div>
    <!-- <router-link :to="{name:'home'}">pokemon list</router-link>
    <router-link :to="{name:'pokemon-id',params:{id:91}}">Pokemon por id</router-link>
    <router-link :to="{name:'about'}">About</router-link> -->

  <CustomLink v-for="link in links" :key="link.to" :link="link"/>

  </div>
</template>

<script>
import { defineAsyncComponent } from 'vue'
export default {
  data(){
    return {
      links:[
      {to:'pokemon-home',name:'pokemon-home'},
      {to:'pokemon-id',name:'pokemon-id',id:20},
      {to:'pokemon-about',name:'pokemon-about'},
        {to:'dbz-characters',name:'DBZ PERSONAJES'},
      {to:'dbz-about',name:'DBZ ABOUT',},
 
      {to:'https://google.com',name:'Google'},

      ]
    }
  },
    components:{
      CustomLink:defineAsyncComponent(()=> import('./CustomLink.vue'))
    }
}
</script>

<style scoped>


div{
    padding: 0 30px;
}

div a {
    font-weight: bold;
    color:green;
    margin: 0 10px;
}

/* div .router-link-exact-active{
color:#42b983
} */
</style>