<script>
import MainHeader from './components/MainHeader.vue';
import MainFooter from './components/MainFooter.vue';


export default {
    components: {
      MainHeader,
      MainFooter
    }
}

</script>

<template>
 <div class="container">

   <MainHeader/>
   <!--<AppMain/>-->
   <router-view></router-view>
   <MainFooter/>
 </div> 
</template>

<style lang="scss">
 @use "./styles/general.scss";
 
</style>
