<template>
  <v-row justify="center" class="space px-16">
    <v-col cols="12" xs="12" sm="6" md="6" v-for="(product, i) in products" :key="i">
      <v-card class="mx-auto rounded-xl" max-width="600" :elevation="5" color="" flat outlined
        style="border: 1px solid;">
        <v-row no-gutters class="card-content">
          <!-- Left Side: Image -->
          <v-col cols="4" class="image-col">
            <div align="center" justify="center">
              <v-img class="img" max-height="200" max-width="200" contain :src="product.img"></v-img>
            </div>
          </v-col>

          <!-- Right Side: Details -->
          <v-col cols="8">
            <v-card-title style="color: black;" class="title">{{ product.title }}</v-card-title>
            <!-- <v-card-title class="grey--text text-grey-darken-1 caption mt-n6" id="subtitle">{{product.subtitle}}</v-card-title> -->
            <v-card-title style="color: black;" class="mt-n4" id="price">{{ product.price }}</v-card-title>

            <v-card-actions class="mx-2 mb-n3 ">
              <v-btn outlined class="mt-n2 add small-btn bordered-btn" @click="decrement(product)">
                <v-icon color="black">mdi-minus</v-icon>
              </v-btn>
              <strong class="mx-2">{{ product.bpm }}</strong>
              <v-btn outlined class="mt-n2 add small-btn bordered-btn" @click="increment(product)">
                <v-icon color="black">mdi-plus</v-icon>
              </v-btn>
            </v-card-actions>

           <div class="btn">
             <v-btn class="mb-2 cart" style="background-color: orange ;">Add cart</v-btn>
            <v-btn class="mb-2 buy" style="background-color: orange ">Buy Now</v-btn>
          </div>
          </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    bpm: 1,
    products: [
      { img: "i1.png", title: "IPhone 15 Pro", subtitle: "15 Pro Max", price: "Price: $1000", bpm: 1, },
      { img: "s24.png", title: "Samsung S24 Ultra", subtitle: "S24 Ultra", price: "Price: $1000", bpm: 1, },
      { img: "vY35.png", title: "Vivo Y35", subtitle: "Y35", price: "Price: $280", bpm: 1, },
      { img: "OFX7U.png", title: "OPPO X7", subtitle: "Find X7 Ultra", price: "Price: $900", bpm: 1, },
      { img: "TC20.png", title: "Tecno camon30", subtitle: "Camon20 Prime 5G", price: "Price: $450", bpm: 1, },
      { img: "XMF3.png", title: "Xiaomi Fold4", subtitle: "Mini Fold4", price: "Price: $920", bpm: 1, },
      { img: "Gp8a.png", title: "Google Pixel 8a", subtitle: "Pixel 8a", price: "Price: $500", bpm: 1, },
      { img: "RN63.png", title: "Realme Narzo 63", subtitle: "Narzo 63", price: "Price: $200", bpm: 1, },
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

<style scoped>
.img {
  width: 100%;
  height: 100%;
  /* Adjusts to fit within its container */
}

.title {
  font-size: x-large;
  color: black;
  font-weight: 900;
  text-align: left;
}

#subtitle {
  font-size: large;
  color: green;
  font-weight: 900;
  text-align: left;
}

#price {
  margin-left: 1rem;
  font-size: large;
  color: black;
  font-weight: 900;
  text-align: left;
}

.green-border {
  border: 2px solid green;
}

.cart {
  margin-left: -5rem;
}

.buy {
  margin-left: 1rem;
}

.v-btn {
  margin-top: 10px;
}

.small-btn {
  padding: 0 !important;
  min-width: 32px !important;
  width: 32px !important;
  height: 32px !important;
  font-weight: 900;
  margin-left: 1rem;
}

.bordered-btn {
  border: 2px solid orangered !important;
  border-radius: 50%;

}
.btn{
  margin-left: 7rem;
}
@media (max-width: 600px) {
  .v-card {
    width: 120% !important; /* Full width for mobile */
    max-width: none !important; /* Remove max-width restriction */
    margin: 0 auto !important; /* Center horizontally */ 
    
  }

  .img {
    margin-top: 2rem;
    max-height: 300px !important; /* Adjust height for mobile */
  }

  .title {
    font-size: large !important; /* Increase font size for mobile */
  }

  #price {
    font-size: medium !important; /* Increase font size for mobile */
  }
  .btn{
    flex: 1 0 45;
    margin-left: 1rem;
  }
 
}

</style>
