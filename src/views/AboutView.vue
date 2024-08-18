<template>
 <v-app>
  <v-main>
    <v-col cols="12" sm="12" class="mt-16">
      <h2 class="mb-4">Popular Products</h2>
      <PopularPro/>
    </v-col>
  </v-main>
 </v-app>
</template>
<script>
import PopularPro from '@/components/PopularPro.vue'
export default{
  name:"AboutView",
  components:{
    PopularPro,
  }
}
</script>