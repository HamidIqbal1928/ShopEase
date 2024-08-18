<template>
    <v-row justify="center" class="space px-16">
      <v-col cols="12" xs="12" sm="6" md="4" v-for="(Image, i) in Images" :key="i">
        <v-card class="mx-auto rounded-xl" max-width="300" :elevation="5" color="" flat outlined style="border: 1px solid black;">
          <div align="center" justify="center">
            <v-img class="img mt-0" max-height="300" max-width="300" style="height: 100px;" contain :src="Image.img"></v-img>
          </div>
  
          <v-card-title class="title">{{ Image.title }}</v-card-title>
          <v-card-title class="grey--text text-grey-darken-1 caption mt-n2" id="subtitle">{{Image.subtitle}}</v-card-title>
          <v-card-title class="mt-n4" id="price">{{ Image.price }}</v-card-title>
  
          <!-- <v-card-actions class="mx-16 mt-1" style="justify-content: center;">
            <v-btn outlined class="mt-n2 add small-btn bordered-btn" @click="decrement(Image)">
              <v-icon color="green">mdi-minus</v-icon>
            </v-btn>
            <strong class="mx-2">{{ Image.bpm }}</strong>
            <v-btn outlined class="mt-n2 add small-btn bordered-btn" @click="increment(Image)">
              <v-icon color="green">mdi-plus</v-icon>
            </v-btn>
          </v-card-actions> -->
          <v-btn class="mb-2" style="background-color: orange; border-radius: 15px;">BuyNow</v-btn>
        </v-card>
      </v-col>
    </v-row>
  </template>
  <script>
  export default{
      data: () => ({
      bpm: 1,
      Images: [
        { img: "i14.png", title: "Apple", subtitle: "Iphone 14", price: "Rs: $1340",bpm:1 },
        { img: "i13.png", title: "Apple ", subtitle: "13 Pro Max", price: "Rs: $1200", bpm:1 },
        { img: "i12.png", title: "Apple", subtitle: " Iphone 12", price: "Rs: $980",bpm:1 },
      ],
    }),
    methods: {
      increment(Image) {
        Image.bpm++;
      },
      decrement(Image) {
        if (Image.bpm > 0) {
            Image.bpm--;
        }
      }
  
    },
  };
  </script>
  
  <style>
  .img{
    width: 80%;
    height: 80vh;
  }
  .title {
    margin-top: 3px;
    margin-bottom: 0px;
    font-size: x-large;
    color:black;
    font-weight: 900;
    text-align: center;
  }
  
  #subtitle {
    font-size: large;
    color: black;
    font-weight: 900;
    text-align: center;
  }
  
  #price {
    font-size: large;
    color: black;
    font-weight: 900;
    text-align: center;
  }
  
  .green-border {
    border: 2px solid black;
  }
  
  .small-btn {
    padding: 0 !important;
    min-width: 32px !important;
    width: 32px !important;
    height: 32px !important;
  }
  .bordered-btn {
    border: 2px solid green !important;
    border-radius: 50%;
   
  }
  .shopping{
    margin-top: 10px;
    font-size: large; 
  }
  </style>