<template>
    <v-container class="order-payment-page">
      <!-- User Details Section -->
      <v-card class="mt-16">
        <v-card-title>User <span style="color: orangered"> Details</span></v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="Name" v-model="user.name" append-inner-icon="mdi-account" variant="outlined" color="orange" required></v-text-field>
            <v-text-field label="Phone Number" v-model="user.phone" append-inner-icon="mdi-phone" variant="outlined" color="orange" required></v-text-field>
            <v-text-field label="Address" v-model="user.address" append-inner-icon="mdi-home" variant="outlined" color="orange" required></v-text-field>
          </v-form>
        </v-card-text>
      </v-card>
  
      <!-- Payment Method Section -->
      <v-card class="mb-4">
        <v-card-title>Payment <span style="color: orangered"> Method</span></v-card-title>
        <v-card-text>
          <v-radio-group v-model="paymentMethod" row>
            <v-radio label="Credit Card" value="credit-card"></v-radio>
            <v-radio label="Jazzcash" value="jazzcash"></v-radio>
            <v-radio label="Easypaisa" value="easypaisa"></v-radio>
            <v-radio label="Cash on Delivery" value="cash"></v-radio>
          </v-radio-group>
          <v-text-field v-if="paymentMethod === 'credit-card'" label="Card Number" v-model="paymentDetails.cardNumber" append-inner-icon="mdi-credit-card" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'credit-card'" label="Expiration Date" v-model="paymentDetails.expiryDate" append-inner-icon="mdi-calendar" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'credit-card'" label="CVV" v-model="paymentDetails.cvv" append-inner-icon="mdi-lock" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'credit-card'" label="Price" v-model="paymentDetails.price" append-inner-icon="mdi-currency-usd" variant="outlined" color="orange" required></v-text-field>
          
          <v-text-field v-if="paymentMethod === 'jazzcash'" label="Account Holder Name" v-model="jazzdetail.accountHolder" append-inner-icon="mdi-account" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'jazzcash'" label="Jazzcash Phone No" v-model="jazzdetail.PhnoneNo" append-inner-icon="mdi-phone" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'jazzcash'" label="Price" v-model="jazzdetail.price" append-inner-icon="mdi-currency-usd" variant="outlined" color="orange" required></v-text-field>
  
          <v-text-field v-if="paymentMethod === 'easypaisa'" label="Account Holder Name" v-model="easypaisaDetail.accountHolder" append-inner-icon="mdi-account" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'easypaisa'" label="EasyPaisa Phone No" v-model="easypaisaDetail.PhnoneNo" append-inner-icon="mdi-phone" variant="outlined" color="orange" required></v-text-field>
          <v-text-field v-if="paymentMethod === 'easypaisa'" label="Price" v-model="easypaisaDetail.price" append-inner-icon="mdi-currency-usd" variant="outlined" color="orange" required></v-text-field>
  
          <v-card-actions>
            <v-btn @click="placeOrder" color="success">Place Order</v-btn>
          </v-card-actions>
        </v-card-text>
      </v-card>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        user: {
          name: '',
          phone: '',
          address: ''
        },
        paymentMethod: '',
        paymentDetails: {
          cardNumber: '',
          expiryDate: '',
          cvv: '',
          price: ''
        },
        jazzdetail: {
          accountHolder: '',
          PhnoneNo: '',
          price: ''
        },
        easypaisaDetail: {
          accountHolder: '',
          PhnoneNo: '',
          price: ''
        },
        orderItems: [
          { id: 1, name: 'Pizza', price: '$10' },
          { id: 2, name: 'Burger', price: '$5' }
        ],
        orderTotal: '$15'
      };
    },
    methods: {
      placeOrder() {
        // Logic to handle order placement
        // For demonstration, we'll just show an alert
        alert('Order placed successfully!');
  
        // Clear the form fields
        this.user = {
          name: '',
          phone: '',
          address: ''
        };
        this.paymentMethod = '';
        this.paymentDetails = {
          cardNumber: '',
          expiryDate: '',
          cvv: '',
          price: ''
        };
        this.jazzdetail = {
          accountHolder: '',
          PhnoneNo: '',
          price: ''
        };
        this.easypaisaDetail = {
          accountHolder: '',
          PhnoneNo: '',
          price: ''
        };
  
        // Optionally, you can reset the form as well
        // this.$refs.form.reset();
      }
    }
  };
  </script>
  
  <style scoped>
  .order-payment-page {
    max-width: 600px;
    margin: 0 auto;
    background-image: url('/public/pd.png'); /* Add your background image path here */
    background-size: cover;
    background-position: center;
    padding: 20px;
  }
  
  .v-card-title {
    font-weight: bold;
  }
  
  .v-text-field, .v-radio-group {
    margin-bottom: 20px;
  }
  
  .v-btn {
    width: 100%;
  }
  </style>
  