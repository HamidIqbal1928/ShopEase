<template>
  <v-item-group mandatory class="mt-n1">
    <v-container>
      <v-row justify="center" class="space">
        <v-col
          cols="12"
          xs="12"
          sm="4"
          md="2"
          v-for="(cetegory, i) in categories"
          :key="i"
        >
          <v-item v-slot="{ active, toggle }">
            <v-card
              id="card"
              :color="active ? '#D5F0DB' : 'white'"
              :class="['d-flex', 'align-center', 'rounded-lg', 'mx-2', active ? 'borderme' : 'borderout']"
              dark
              height="180"
              @click="toggle"
              flat
            >
              <v-row>
                <v-col cols="12" sm="12">
                  <v-list-item three-line class="text-center">
                    <v-list-item-content>
                      <div align="center" justify="center">
                        <v-img
                          :src="cetegory.img"
                          max-height="80"
                          max-width="80"
                          contain
                        ></v-img>
                      </div>
                      <v-list-item-subtitle
                        id="subtitle"
                        :class="active ? 'green--text' : 'black--text'"
                        class="caption mt-4"
                      >
                        {{ cetegory.title }}
                      </v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </v-col>
              </v-row>
            </v-card>
          </v-item>
        </v-col>
      </v-row>
    </v-container>
  </v-item-group>
</template>

<script>
export default {
  data: () => ({
    categories: [
      { img: "SBF.png", title: "Mobiles" },
      { img: "earbud.png", title: "Earbuds" },
      { img: "smart.png", title: "Watches" },
      { img: "charger.png", title: "Chargers" },
      { img: "tablet.png", title: "Tablets" },
      { img: "laptop.png", title: "Laptops" },
    ],
  }),
};
</script>

<style scoped>
#card {
  transition: border-color 0.3s, background-color 0.3s, color 0.3s;
  border: 2px solid transparent;
}
.borderme {
  border-color: orangered !important;
}
.borderout {
  border-color: #ccc !important;
}

#card:hover {
  border-color: orangered !important;
  color: white !important;
}

#subtitle {
  color: rgb(239, 71, 11) !important;
  margin-bottom: 0 !important; /* Adjusted to remove extra space */
}

.green--text {
  color: rgb(199, 103, 68) !important;
}

.black--text {
  color: black !important;
}
</style>
