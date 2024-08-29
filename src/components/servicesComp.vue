<template>
  <v-row justify="center" class="space px-16">
    <v-col cols="12" xs="12" sm="6" md="4" v-for="(card, i) in cards" :key="i">
      <v-card class="mx-auto" max-width="344">
        <v-img height="200px" :src="card.img" cover></v-img>

        <v-card-title style="font-size: x-large;">{{ card.title }}</v-card-title>

        <v-card-subtitle>{{ card.subtitle }}</v-card-subtitle>

        <v-card-actions>
          <v-btn color="orange-lighten-2" text>Explore</v-btn>

          <v-spacer></v-spacer>

          <v-btn :icon="card.show ? 'mdi-chevron-up' : 'mdi-chevron-down'" @click="toggleCard(card)"></v-btn>
        </v-card-actions>

        <v-expand-transition>
          <div v-show="card.show">
            <v-divider></v-divider>

            <v-card-text>{{ card.text }}</v-card-text>
          </div>
        </v-expand-transition>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    cards: [
      {
        img: "https://img.freepik.com/premium-vector/logistics-delivery-online-service-mobile-global-logistic-online-order-digital-marketing-truck-warehouse-parcel-box-concept-website-banner-3d-vector-illustration_473922-74.jpg",
        title: "Fast Delivery",
        subtitle: "The percel deliver as soon as possible.",
        text: "Fast delivery services are designed to ensure that your parcel reaches you as quickly as possible. These services prioritize customer convenience and satisfaction, making it easy for you to receive your items promptly. In today’s fast-paced world, where time is of the essence, fast delivery services have become essential. Whether you are located in a remote area or in the heart of the city, these services ensure that your parcel is delivered swiftly and securely.",
        show: false,
      },
      {
        img: "https://res.cloudinary.com/apudos/images/f_auto,q_auto/v1689940322/Safe-and-Secure-Packaging-Made-Easy_7957464f24/Safe-and-Secure-Packaging-Made-Easy_7957464f24.jpg?_i=AA",
        title: "Safe and Secure Packing",
        subtitle: "Safe and secure packing of the product.",
        text: "Safe and secure packing is crucial in ensuring that your items reach their destination in perfect condition. Proper packaging protects your goods from damage during transit, whether they are fragile electronics, delicate glassware, or everyday items. By using high-quality materials like sturdy boxes, bubble wrap, and protective cushioning, safe packing minimizes the risk of breakage, crushing, or moisture damage.",
        show: false,
      },
      {
        img: "https://storage.googleapis.com/kargotech-web/2021/04/2c62d357-cash-on-delivery.jpeg",
        title: "Cash on Delivery",
        subtitle: "First check the percel then pay for it.",
        text: "Cash on Delivery (COD) is a convenient payment method that allows you to pay for your purchase only when it arrives at your doorstep. This service offers a sense of security and trust, as you can inspect the item before making the payment. COD is especially beneficial for those who prefer not to use online payment methods or who want to ensure that the product meets their expectations before committing to the purchase. ",
        show: false,
      },
      {
        img: "https://koronapos.com/wp-content/uploads/2020/08/806036_5-New-Blog-Images-5_081820-1.png",
        title: "Return Policy",
        subtitle: "If any issue then return the percel.",
        text: "Our 2-day return policy ensures that you have peace of mind with your purchase. If you encounter any issues with your product, you can return it within two days of delivery for a full refund or exchange. This policy allows you to inspect the item and make sure it meets your expectations. Whether it's a defect, damage, or simply not what you expected, you can initiate a return easily. We strive to make the process as smooth as possible, ensuring your satisfaction with every purchase.",
        show: false,
      },
      {
        img: "https://th.bing.com/th/id/R.b4b1c05b8ffd0d5f51900fd7a3883f3b?rik=3aT6YlRbwsjlAw&pid=ImgRaw&r=0",
        title: "Return Policy",
        subtitle: "No cumpromise on the quality.",
        text: "We are committed to providing exceptional value by offering products of high quality at competitive prices. Our focus is on ensuring that you receive top-notch items without compromising your budget. By leveraging efficient sourcing and streamlined operations, we are able to keep costs low while maintaining rigorous quality standards. This means you can enjoy durable, reliable products that meet your needs, all while benefiting from affordable pricing. Our goal is to deliver excellent quality and value, making sure you get the best for less.",
        show: false,
      },
    ],
  }),
  methods: {
    toggleCard(card) {
      card.show = !card.show;
    },
  },
};
</script>

<style scoped>
.space {
  margin-top: 20px;
}
@media (max-width: 600px) {
  .card {
    max-width: 100% !important;
    width: 100% !important; /* Full width for mobile */
    margin: 0 auto !important; /* Center horizontally */
  }
}
</style>
