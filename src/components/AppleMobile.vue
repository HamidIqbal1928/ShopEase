<template>
  <v-app class="mt-16">
    <v-main>
          <v-row dense no-gutters class="mr-4 ml-4 mb-2">
        <v-col cols="12" xs="12" sm="6" md="4" lg="3" v-for="(product, i) in products" :key="i">
          <v-card class="mx-auto rounded-xl mt-1" max-width="300" color="" flat outlined style="border: 2px solid orangered;">
            <div align="center" justify="center">
              <v-img max-height="200" max-width="300" contain :src="product.img"></v-img>
            </div>

            <v-card-title class="title">{{ product.title }}</v-card-title>
            <v-card-title class=" text-grey-darken-1 caption mt-n6" id="subtitle">{{product.subtitle}}</v-card-title>
            <v-card-title class="mt-n4" id="price">{{ product.price }}</v-card-title>

            <v-card-actions class="mx-16 mt-1" style="justify-content: center;">
              <v-btn outlined class="mt-n2 add small-btn bordered-btn" @click="decrement(product)">
                <v-icon color="black">mdi-minus</v-icon>
              </v-btn>

              <strong class="mx-2">{{ product.bpm }}</strong>
              <v-btn outlined class="mt-n2 add small-btn bordered-btn" @click="increment(product)">
                <v-icon color="black">mdi-plus</v-icon>
              </v-btn>

              <div class="btn">
                <v-btn class="mx-2 mt-n3 small-btn bordered-btn" fab dark small color="black">
                  <v-icon dark>mdi-shopping</v-icon>
                </v-btn>
                <v-btn class="mx-2 mt-n3 small-btn bordered-btn" fab dark small color="black">
                  <v-icon dark>mdi-heart</v-icon>
                </v-btn>
              </div>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>


<script>
export default {
  data: () => ({
    bpm: 1,
    products: [
    { img: "SBF.png", title: " Latest Mobile phones", subtitle: "1btl-100btl", price: "Price: $1000",bpm:1},
    { img: "i14.png", title: " Latest Mobile phones", subtitle: "1btl-100btl", price: "Price: $1000",bpm:1},
    { img: "s24.png", title: " Latest Mobile phones", subtitle: "1btl-100btl", price: "Price: $1000",bpm:1},
    { img: "vY35.png", title: " Latest Mobile phones", subtitle: "1btl-100btl", price: "Price: $1000",bpm:1},

      { img: "earbud.png", title: " Bluetooth Earbuds", subtitle: "1pc-13pc", price: "Price: $13", bpm:1 },
    { img: "eb1.png", title: " Bluetooth Earbuds", subtitle: "1pc-13pc", price: "Price: $13", bpm:1 },
    { img: "eb2.png", title: " Bluetooth Earbuds", subtitle: "1pc-13pc", price: "Price: $13", bpm:1 },
    { img: "eb3.png", title: " Bluetooth Earbuds", subtitle: "1pc-13pc", price: "Price: $13", bpm:1 },

      { img: "smart.png", title: "Smart Watches", subtitle: "1pc-20pc ", price: "Price: $52",bpm:1 },
      { img: "w2.png", title: "Smart Watches", subtitle: "1pc-20pc ", price: "Price: $52",bpm:1 },
      { img: "w3.png", title: "Smart Watches", subtitle: "1pc-20pc ", price: "Price: $52",bpm:1 },
      { img: "w4.png", title: "Smart Watches", subtitle: "1pc-20pc ", price: "Price: $52",bpm:1 },

      { img: "tablet.png", title: "Latest Tablet", subtitle: "ipad,sumsung,Android", price: "Price: $1400",bpm:1 },
      { img: "t2.png", title: "Latest Tablet", subtitle: "ipad,sumsung,Android", price: "Price: $1400",bpm:1 },
      { img: "t3.png", title: "Latest Tablet", subtitle: "ipad,sumsung,Android", price: "Price: $1400",bpm:1 },
      { img: "t4.png", title: "Latest Tablet", subtitle: "ipad,sumsung,Android", price: "Price: $1400",bpm:1 },

      { img: "laptop.png", title: "Sumsung Laptop", subtitle: "1kpc-5pc", price: "Price: $10",bpm:1 },
      { img: "l1.png", title: "Sumsung Laptop", subtitle: "1kpc-5pc", price: "Price: $10",bpm:1 },
      { img: "l2.png", title: "Sumsung Laptop", subtitle: "1kpc-5pc", price: "Price: $10",bpm:1 },
      { img: "l3.png", title: "Sumsung Laptop", subtitle: "1kpc-5pc", price: "Price: $10",bpm:1 },

    { img: "charger.png", title: "chargers", subtitle: "1c-50pc", price: "Price: $10",bpm:1 },
    { img: "c2.png", title: "chargers", subtitle: "1c-50pc", price: "Price: $10",bpm:1 },
    { img: "c3.png", title: "chargers", subtitle: "1c-50pc", price: "Price: $10",bpm:1 },
    { img: "c4.png", title: "chargers", subtitle: "1c-50pc", price: "Price: $10",bpm:1 },

    ],
  }),
  methods: {
    increment(product) {
      product.bpm++;
    },
    decrement(product) {
      if (product.bpm > 0) {
        product.bpm--;
      }
    }

  },
};
</script>

<style>
.title {
  margin-top: 23px;
  margin-bottom: 5px;
  font-size: x-large;
  color: green;
  font-weight: 900;
  text-align: center;
}

#subtitle {
  font-size: large;
  color: green;
  font-weight: 900;
  text-align: center;
}

#price {
  font-size: large;
  color: green;
  font-weight: 900;
  text-align: center;
}

.green-border {
  border: 2px solid orangered;
}
.btn{
  display: flex;
  flex-direction: row;
  margin-left: 2rem;
}


.small-btn {
  padding: 0 !important;
  min-width: 32px !important;
  width: 32px !important;
  height: 32px !important;
}
.bordered-btn {
  border: 2px solid rgb(240, 67, 4) !important;
  border-radius: 50%;
 
}
.shopping{
  margin-top: 10px;
  font-size: large;
  
  
  
}

</style>
