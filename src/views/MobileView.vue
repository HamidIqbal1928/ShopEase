<template>
  <v-app>
    <v-app-bar app color="white" flat>
      <v-toolbar-title class="ml-4">
        <strong>Shop</strong><span class="etext">Ease</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="mr-1"></v-app-bar-nav-icon>

      <v-menu offset-y class="custom-menu" id="circular-icon">
        <template v-slot:activator="{ props }">
          <v-btn icon v-bind="props" class="menu-icon">
            <v-img :src="userImage" contain width="30" v-if="userImage"></v-img>
            <v-icon width="50" v-else>mdi-account-circle</v-icon>
          </v-btn>
        </template>
        <v-list v-if="currentUser" class="menu-list">
          <v-list-item class="menu-list-item">
            <v-list-item-avatar>
              <v-avatar size="40" class="avatar">
                <v-img :src="userImage" contain v-if="userImage"></v-img>
                <v-icon v-else>mdi-account-circle</v-icon>
              </v-avatar>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title class="menu-title">{{ currentUser.name }}</v-list-item-title>
              <v-list-item-subtitle class="menu-subtitle">{{ currentUser.email }}</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item @click="logout">
            <v-list-item-title class="logout-btn">
              <v-icon color="blue-darken-2 mr-1 mb-1">mdi-logout</v-icon>Logout
            </v-list-item-title>
          </v-list-item>
        </v-list>
        <v-list v-else>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>No user logged in</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app temporary class="bar" color="white">
      <v-list-item></v-list-item>
      <v-list-item-group>
        <v-list class="item-group">
          <v-list-item
            v-for="link in links"
            :key="link.id"
            :to="link.route"
            :ripple="false"
            class="routelinks"
          >
            <v-icon>{{ link.icon }}</v-icon>
            <span class="ml-4">{{ link.name }}</span>
          </v-list-item>
        </v-list>

        <div class="badge">
          <v-badge color="#FF6D59" overlap content="2" class="mr-2 mt-1 mb-1">
            <v-avatar color="#FFF0EE" size="30">
              <v-icon xx-small color="#FF6D59">mdi-heart</v-icon>
            </v-avatar>
          </v-badge>
          <v-badge color="#41AB55" overlap content="3" class="ml-4 mt-1">
            <v-avatar color="#ECF7EE" size="30">
              <v-icon x-small color="#41AB55">mdi-cart</v-icon>
            </v-avatar>
          </v-badge>
        </div>
      </v-list-item-group>
    </v-navigation-drawer>
  </v-app>
</template>


<script>
export default {
  name: "MobileView",
  data: () => ({
    currentUser: null,
    drawer: false,
    links: [
      { name: "Home", route: "/", icon: "mdi-home" },
      { name: "Products", route: "/product", icon: "mdi-information" },
      { name: "Bundles", route: "/bundle", icon: "mdi-newspaper-variant" },
      { name: "Contact Us", route: "/contact", icon: "mdi-chevron-right" },
    ],
  }),
  mounted() {
    this.getCurrentUser();
    this.checkLoggedIn();
  },
  methods: {
    getCurrentUser() {
      const storedItems = JSON.parse(localStorage.getItem('itemsJson'));
      const userEmail = localStorage.getItem('userEmail');

      if (storedItems && userEmail) {
        this.currentUser = storedItems.find(item => item.email === userEmail);
      }
    },
    checkLoggedIn() {
      if (localStorage.getItem('isLoggedIn')) {
        this.loginForm = false;
      }
    },
    logout() {
      localStorage.removeItem('isLoggedIn');
      localStorage.removeItem('userEmail');
      localStorage.removeItem('userData');
      this.currentUser = null;
      this.$router.push('/login');
    },
  },
};
</script>

<style scoped>
html, body, #app {
  height: 100%;
  margin: 0;
  padding: 0;
}

.v-application {
  display: flex;
  flex-direction: column;
  min-height: 100%;
}

.main-content {
  flex-grow: 1;
}

.footer {
  background-color: #1976D2 !important;
  color: white;
  text-align: center;
}

.v-list-item-avatar {
  margin-right: 16px;
}

.custom-menu .v-list {
  background-color: #f5f5f5;
  border-radius: 18px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.custom-menu .menu-list-item {
  border-bottom: 1px solid #ddd;
}

.custom-menu .menu-list-item:last-child {
  border-bottom: none;
}

.menu-title {
  font-weight: bold;
  margin-left: 1rem;
  margin-right: 1rem;
  color: #333;
}

.menu-subtitle {
  margin-bottom: 1rem;
  margin-left: 0.5rem;
  color: #777;
}

.menu-icon {
  color: #1976D2;
}

.avatar {
  margin-left: 2.5rem;
}

.logout-btn {
  color: blue;
}

.badge {
  margin-left: 3rem;
  margin-top: 1rem;
}

.routelinks {
  font-weight: bold;
  color: orangered;
  text-decoration: none;
  padding: 10px 20px;
  transition: background-color 0.3s, color 0.3s;
  display: inline-block;
  margin-left: 2rem;
  margin-top: 0.3rem;
}

.routelinks:hover {
  color: black;
  text-decoration: none;
}

.etext {
  color: orangered;
  font-size: large;
  font-weight: 900;
}

.bar {
  background-color: 'primary';
}
</style>
