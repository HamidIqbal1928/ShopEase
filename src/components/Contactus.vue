<template class="mt-16">
    <div>
      <div style="display: flex; justify-content: center;">
    <h1 style="margin-top: 80px; margin-bottom: 0px; text-align: center;">
        Contact <span style="color: orangered;">Us</span>
    </h1>
</div>      <v-sheet class="mx-auto mt-16" max-width="400">
        <v-form @submit.prevent ref="form">
          <v-text-field v-model="userData.name" class="text-black" label="Name" append-inner-icon="mdi-account"
            variant="outlined" color="blue" :counter="20" :rules="dataValidationRules.name" required>
          </v-text-field>
          <v-text-field v-model="userData.email" label="Email" append-inner-icon="mdi-email" variant="outlined"
            color="blue" hint="www.example@gmail.com" :rules="dataValidationRules.email"></v-text-field>
          <!-- <v-text-field v-model="userData.password" label="Password" append-inner-icon="mdi-eye" variant="outlined"
            color="blue"></v-text-field> -->
          <v-text-field v-model="userData.phNumber" label="Phone No" append-inner-icon="mdi-phone No" variant="outlined"
            color="blue" :rules="dataValidationRules.phone"></v-text-field>
          <v-textarea v-model="userData.address" label="Address" rows="2" clear-icon="mdi-close-circle" clearable
            append-inner-icon="mdi-home" variant="outlined" :rules="dataValidationRules.address" color="blue">
          </v-textarea>
  <v-checkbox type="checkbox" label="Add Amount" v-on:click="AddBonus()">
  
  </v-checkbox>
  <div v-if="addBonus">
    <v-text-field  v-model="userData.bonus" label="spending Amount"  variant="outlined"
    color="blue">
    </v-text-field>
  </div>
  
          <v-btn class="mt-2" type="submit" color="success" block v-on:click="logUserData()">
            submit
          </v-btn>
          <v-btn class="mt-2" block v-on:click="clearForm()">
            Clear
          </v-btn>
          <br>
        </v-form>
      </v-sheet>
    </div>
  </template>
  <script>
  export default {
    name: 'TestComponent',
  
  
    data() {
      return {
      addBonus:false,
        userData: {
          name: '',
          email: '',
          phNumber: '',
          address: '',
          bonus:0
        },
        desserts: [
{
  name: 'Frozen Yogurt',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20,
},
{
  name: 'Ice cream sandwich',
  email:" numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'Eclair',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
     name: 'Frozen Yogurt',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'Gingerbread',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'Jelly bean',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'Lollipop',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'Honeycomb',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'Donut',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
{
  name: 'KitKat',
  email: "numanrazzaq24@gmail.com",
  phNo:"030417926254",
  password:"*********",
  address:"24 Wb Vehari",
  age:20
},
],
        dataValidationRules: {
          name: [
            value => {
              if (value) return true
              return 'You must enter a Name.'
            },
          ],
          phone: [
            value => {
              if (value?.length > 9 && /[0-9-]+/.test(value)) return true
  
              return 'Phone number needs to be at least 9 digits.'
            },],
          email: [
            value => {
              if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true
  
              return 'Must be a valid e-mail.'
            },],
  
          address: [
            value => {
              if (value?.length > 25) return true
              return 'Address must be at least 25 characters.'
            }
          ]
        }
      }
  
    },
    methods: {
      logUserData() {
        console.log(this.desserts);
        // console.log(this.userData);
        this.desserts.push(this.userData);
        console.log(this.desserts);
      },
      clearForm(){
        this.userData.name='';
        this.userData.address='';
        this.userData.email='';
        this.userData.password='';
        this.userData.phNumber='';
        this.reset();
        },
        reset () {
          this.$refs.form.reset()
        },  
        AddBonus(){
          this.addBonus= !this.addBonus;
        }    
    }
  }
  
  
  </script>