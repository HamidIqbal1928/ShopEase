<template>
    <v-app>
        <v-main>
            <Contactus/>
        </v-main>
    </v-app>
</template>
<script>
import Contactus from '@/components/Contactus.vue';

export default{
    name:"ContactView",
    components:{
        Contactus
    }
}
</script>