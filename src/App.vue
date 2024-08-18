<template>
  <div>
    <div v-if="loginForm">
      <v-card class="mx-auto mt-16 pa-12 pb-8" elevation="8" max-width="448" rounded="lg">
        <div class="text-subtitle-1 text-medium-emphasis">Account</div>

        <v-text-field density="compact" placeholder="Email address" prepend-inner-icon="mdi-email-outline"
          variant="outlined" v-model="userData.email" :rules="dataValidationRules.email" required></v-text-field>

        <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
          Password
          <a class="text-caption text-decoration-none text-blue" href="#" rel="noopener noreferrer" target="_blank">
            Forgot login password?</a>
        </div>

        <v-text-field :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'" :type="visible ? 'text' : 'password'"
          density="compact" placeholder="Enter your password" prepend-inner-icon="mdi-lock-outline" variant="outlined"
          @click:append-inner="visible = !visible" :rules="dataValidationRules.password" required
          v-model="userData.password"></v-text-field>

        <v-card class="mb-12" color="surface-variant" variant="tonal">
          <v-card-text class="text-medium-emphasis text-caption">
            Warning: After 3 consecutive failed login attempts, your account will be temporarily locked for three hours.
            If you must login now, you can also click "Forgot login password?" below to reset the login password.
          </v-card-text>
        </v-card>

        <v-btn class="mb-8" type="submit" color="blue" size="large" variant="tonal" block v-on:click="login()">
          Log In
        </v-btn>

        <v-card-text class="text-center">
          <v-btn @click="dialogAddUser = true" class="Btn" color="blue">
            Sign Up
            <v-icon icon="mdi-account" class="ml-3"></v-icon>
          </v-btn>

          <v-dialog v-model="dialogAddUser" transition="dialog-top-transition" max-width="600">
            <v-card title="Add New User Details">
              <template v-slot:text>
                <div>
                  <div class="text-subtitle-1 text-medium-emphasis">Name</div>
                  <v-text-field density="compact" placeholder="Enter Name" prepend-inner-icon="mdi-account"
                    v-model="userData.name" variant="outlined" color="blue" :rules="dataValidationRules.name"
                    required></v-text-field>

                  <div class="text-subtitle-1 text-medium-emphasis">Account</div>
                  <v-text-field density="compact" placeholder="Email address" prepend-inner-icon="mdi-email-outline"
                    variant="outlined" v-model="userData.email" color="blue" :rules="dataValidationRules.email"
                    required></v-text-field>

                  <div class="text-subtitle-1 text-medium-emphasis d-flex align-center justify-space-between">
                    Password
                  </div>
                  <v-text-field :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
                    :type="visible ? 'text' : 'password'" density="compact" placeholder="Enter your password"
                    prepend-inner-icon="mdi-lock-outline" variant="outlined" color="blue" v-model="userData.password"
                    @click:append-inner="visible = !visible" required></v-text-field>

                  <div class="text-subtitle-1 text-medium-emphasis">Address</div>
                  <v-text-field density="compact" placeholder="Enter Address" prepend-inner-icon="mdi-home"
                    v-model="userData.address" variant="outlined" :rules="dataValidationRules.address" color="blue"
                    required></v-text-field>
                </div>
              </template>

              <template v-slot:actions>
                <v-btn class="ms-auto" color="red" text="Close" @click="dialogAddUser = false">
                  Close
                  <v-icon icon="mdi-minus-circle" end></v-icon>
                </v-btn>
                <v-spacer></v-spacer>
                <v-btn class="ms-auto" color="primary" text="Add" @click="logUserData()">
                  Submit
                  <v-icon icon="mdi-checkbox-marked-circle" end></v-icon>
                </v-btn>
              </template>
            </v-card>
          </v-dialog>
        </v-card-text>
      </v-card>
    </div>
    <div v-else>
      <div class="home-view">
        <AllView />
      </div>
      <div class="mobile-view">
        <MobileView />
      </div>
    </div>

  </div>
</template>

<script>
import MobileView from '@/views/MobileView.vue';
// import p1 from './assets/hamid.png';
// import p2 from './assets/noman.png';
import AllView from './views/AllView.vue';

export default {
  name: "App",
  components: {
    MobileView,
    AllView
  },
  data() {
    return {
      dialogAddUser: false,
      userData1: {
        name: '',
        email: '',
        address: '',
        password: '',
        age: 0
      },
      userData: {
        email: '',
        password: '',
      },
      itemArray: [],
      usersArray: [
        {
          name: "Muhammad Numan",
          email: "numanrazzaq123@gmail.com",
          password: "12345678",
          // image: p2,
          phNo: "03041792624",
          address: "Chak no 24 Wb Vehari",
          login: false
        },
        {
          name: "Hamid",
          email: "hamid313500@gmail.com",
          password: "12345678",
          // image: p1,
          phNo: "03041792624",
          address: "Chak no 28 Wb Vehari",
          login: false
        }
      ],
      loginForm: true,
      dataValidationRules: {
        email: [
          value => {
            if (/^[a-z.-]*\d{3,10}[a-z.-]*@[a-z.-]+\.[a-z]+$/i.test(value)) {
              return true;
            }
            return 'Email must be valid and contain between 3 and 10 numbers before the @ symbol.';
          },
        ],
        password: [
          value => {
            if (value?.length >= 8 && /[0-9-]+/.test(value)) return true;
            return 'Password needs to be at least 8 digits.';
          },
        ],
      },
      visible: false
    };
  },
  beforeMount() {
    this.fetchData();
    this.checkLoggedIn();
    this.update();
  },
  mounted() {
    window.addEventListener('resize', this.checkScreenSize);
    this.checkScreenSize();
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.checkScreenSize);
  },
  methods: {
    fetchData() {
      if (localStorage.getItem('itemsJson') == null) {
        this.itemArray = this.usersArray;
        localStorage.setItem('itemsJson', JSON.stringify(this.itemArray));
      }
    },
    update() {
      if (localStorage.getItem('itemsJson') == null) {
        this.itemsArray = this.usersArray;
        localStorage.setItem('itemsJson', JSON.stringify(this.itemsArray));
      } else {
        this.newitemsinArray = localStorage.getItem('itemsJson');
        this.itemsArray = JSON.parse(this.newitemsinArray);
      }
    },
    logUserData() {
      this.itemArray.push({
        name: this.userData.name,
        email: this.userData.email,
        address: this.userData.address,
        password: this.userData.password,
        age: this.userData.age
      });
      localStorage.setItem('itemsJson', JSON.stringify(this.itemArray));
      this.clearForm();
      this.dialogAddUser = false;
    },
    clearForm() {
      this.userData.name = '';
      this.userData.address = '';
      this.userData.email = '';
      this.userData.password = '';
      this.userData.age = 0;
    },
    checkLoggedIn() {
      if (localStorage.getItem('isLoggedIn')) {
        this.loginForm = false;
      }
    },
    login() {
      const userEmail = this.userData.email;
      const storedItems = JSON.parse(localStorage.getItem('itemsJson'));
      const user = storedItems.find(item => this.userData.email === item.email);

      if (user) {
        if (this.userData.email === user.email && this.userData.password === user.password) {
          localStorage.setItem('isLoggedIn', true);
          localStorage.setItem('userEmail', userEmail);
          this.loginForm = false;
          this.$router.push('/');
        } else {
          alert('Invalid credentials');
        }
      }
    },
    signUp() {
      this.$router.push('/signup');
    },
    checkScreenSize() {
      this.isDesktop = window.innerWidth >= 960;
    }
  }
};
</script>

<style scoped>
.header-view {
  display: none;
}

.mobile-view {
  display: block;
}

@media (min-width: 960px) {
  .header-view {
    display: block;
  }

  .mobile-view {
    display: none;
  }
}
</style>
