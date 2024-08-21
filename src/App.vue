<script>
import MainHeader from './components/MainHeader.vue';
import AppMain from './components/AppMain.vue';
import MainFooter from './components/MainFooter.vue';


export default {
    components: {
      MainHeader,
      AppMain,
      MainFooter
    }
}

</script>

<template>
 <div class="container">

   <MainHeader/>
   <AppMain/>
   <MainFooter/>
 </div> 
</template>

<style lang="scss">
 @use "./styles/general.scss";
 
</style>
