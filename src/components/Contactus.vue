<template>
  <v-container class="mt-16">
    <v-row >
      <!-- Contact Card -->
      <v-col cols="12">
        <v-sheet class="contact-card" max-width="800" tile>
          <v-row>
            <!-- Contact Us Form (Left Side) -->
            <v-col cols="12" md="6">
              <v-sheet class="contact-form">
                <h1 class="text-center">Contact <span style="color: orangered;">Us</span></h1>
                <v-form @submit.prevent ref="form">
                  <v-text-field 
                    v-model="userData.name" 
                    class="text-black" 
                    label="Name" 
                    append-inner-icon="mdi-account"
                    variant="outlined" 
                    color="blue" 
                    :counter="20" 
                    :rules="dataValidationRules.name" 
                    required
                  ></v-text-field>
                  <v-text-field 
                    v-model="userData.email" 
                    label="Email" 
                    append-inner-icon="mdi-email" 
                    variant="outlined"
                    color="blue" 
                    hint="www.example@gmail.com" 
                    :rules="dataValidationRules.email"
                  ></v-text-field>
                  <v-text-field 
                    v-model="userData.phNumber" 
                    label="Phone No" 
                    append-inner-icon="mdi-phone" 
                    variant="outlined"
                    color="blue" 
                    :rules="dataValidationRules.phone"
                  ></v-text-field>
                  <v-textarea 
                    v-model="userData.address" 
                    label="Address" 
                    rows="2" 
                    clear-icon="mdi-close-circle" 
                    clearable
                    append-inner-icon="mdi-home" 
                    variant="outlined" 
                    :rules="dataValidationRules.address" 
                    color="blue"
                  ></v-textarea>
                  <v-btn class="mt-2" type="submit" color="success" block @click="logUserData()">
                    Submit
                  </v-btn>
                  <v-btn class="mt-2" block @click="clearForm()">
                    Clear
                  </v-btn>
                </v-form>
              </v-sheet>
            </v-col>

            <!-- Contact Information (Right Side) -->
            <v-col cols="12" md="6">
              <v-sheet class="contact-info">
                <h1 class="text-center">Contact <span style="color: orangered;">Information</span></h1>
                <div class="ml-15 mt-10">
                <h3 class="address"><strong>Address</strong></h3>
                <ul class="info-list">
                  <li><p>28 Wb Vehari</p></li>
                  <li><p>24 Wb Vehari</p></li>
                </ul>
                <h3><strong>Email:</strong></h3>
                <ul class="info-list">
                  <li><p>hamid313500@gmail.com</p></li>
                  <li><p>numanrazzaq24@gmail.com</p></li>
                  <li><p>azizurrehman2430@gmail.com</p></li>
                </ul>
                <h3><strong>Phone No:</strong></h3>
                <ul class="info-list">
                  <li><p>0319 7286163</p></li>
                  <li><p>0318 4842724</p></li>
                  <li><p>0314 7265924</p></li>
                </ul>
              </div>
              </v-sheet>
            </v-col>
          </v-row>
        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'ContactUsComponent',

  data() {
    return {
      userData: {
        name: '',
        email: '',
        phNumber: '',
        address: ''
      },
      dataValidationRules: {
        name: [
          value => !!value || 'You must enter a Name.'
        ],
        phone: [
          value => (value?.length > 9 && /[0-9-]+/.test(value)) || 'Phone number needs to be at least 9 digits.'
        ],
        email: [
          value => /^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value) || 'Must be a valid e-mail.'
        ],
        address: [
          value => (value?.length > 25) || 'Address must be at least 25 characters.'
        ]
      }
    }
  },
  methods: {
    logUserData() {
      console.log(this.userData);
      // Logic to handle user data
    },
    clearForm() {
      this.userData = {
        name: '',
        email: '',
        phNumber: '',
        address: ''
      };
      this.$refs.form.reset();
    }
  }
}
</script>

<style scoped>
.contact-card {
  /* text-align: center; */
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px orangered;
}

.contact-form, .contact-info {
  padding: 20px;
}

.contact-form {
  /* Styling for contact form */
}

.contact-info {
  /* Styling for contact information */
}

.address {
  font-weight: bold;
}

.info-list {
  /* list-style: none; */
  padding: 0;
  /* text-align: center;     */
}

.info-list li {
  /* margin: 5px 0; */
}

@media (max-width: 600px) {
  .contact-form, .contact-info {
    margin: 0;
  }
}
</style>
