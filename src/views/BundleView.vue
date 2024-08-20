<template>
    <v-app>
     <v-main>
       <v-col cols="12" sm="12" class="mt-16">
        <v-toolbar flat color="transparent">
            <v-toolbar-title class="text-h4" id="title"> Trending Products  </v-toolbar-title>
      </v-toolbar>
         <FeaturePro/>
       </v-col>
     </v-main>
    </v-app>
   </template>
   <script>
   import FeaturePro from '@/components/FeaturePro.vue';
   export default{
     name:"BundleView",
     components:{
        FeaturePro,
     }
   }
   </script>
   <style>
  #title {
  margin-top: 23px;
  margin-bottom: 23px;
  font-size: x-large;
  color: rgb(199, 103, 68);
  font-weight: 900;
  text-align: center;
}</style>