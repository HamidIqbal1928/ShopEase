<template>
    <v-app>
     <v-main>
       <v-col cols="12" sm="12" class="mt-16">
         <h2 class="mb-4">Popular Products</h2>
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