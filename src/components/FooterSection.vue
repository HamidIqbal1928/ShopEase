<template>
  <v-footer dark padless class="footer">
    <v-card flat tile class="black white--text py-12 px-5 footer " width="100%">
      <v-row>
        <v-col cols="12" xs="12" sm="6" md="4" class="pa-16">
          <v-toolbar color="transparent" flat>
          <!-- <v-badge color="#D5F0DB" dot>
           <v-img src="sh1.png" contain width="10"></v-img>
          </v-badge> -->

            <v-toolbar-title class="">
              <strong class="heading">Shop<span style="color: orange">Ease</span></strong>
            </v-toolbar-title>
          </v-toolbar>
          <div class="icon ml-1">
            <v-btn icon href="https://www.facebook.com/hamid.iqbal.12576049?mibextid=ZbWKwL" target="blank"
              class="mt-6 mr-2 face">
              <v-icon size="30" color="blue-darken-2">mdi-facebook</v-icon>
            </v-btn>
            <v-btn icon href="https://github.com/HamidIqbal1928?tab=repositories"  target="blank" class="mt-6 mr-2">
              <v-icon size="30" center>mdi-github</v-icon>
            </v-btn>
            <v-btn icon href="https://www.linkedin.com/in/hamid-iqbal-a50430247/" target="blank" class="mt-6 mr-2">
              <v-icon size="30" color="blue">mdi-linkedin</v-icon>
            </v-btn>
            <v-btn icon href=" https://www.instagram.com/hamid_iqbal77?igsh=eTk5YzNvdjFpdXNq "
              target="_blank" class="mt-6 mr-2">
              <v-icon size="30" color="red">mdi-instagram</v-icon>
            </v-btn>
          </div>
        </v-col>
        <v-col cols="12" xs="12" sm="6" md="2">
          <v-card-text class="white--text pt-0">
            <h3 class="heading">A<span style="color: orange">bou</span>t</h3>
          </v-card-text>
          <v-card-text class="grey--text"> How it <span style="color: orange">Work</span> </v-card-text>
          <v-card-text class="grey--text mt-n4"> Our <span style="color: orange">Programs</span>  </v-card-text>
          <v-card-text class="grey--text mt-n4"> Pro<span style="color: orange">motion</span>s </v-card-text>
          <v-card-text class="grey--text mt-n4"> Refer A <span style="color: orange">Friend</span>  </v-card-text>
        </v-col>
        <v-col cols="12" xs="12" sm="6" md="2">
          <v-card-text class="white--text pt-0">
            <h3 class="heading">De<span style="color: orange">live</span>ry</h3>
          </v-card-text>
          <v-card-text class="grey--text"> Cost of <span style="color: orange">delivery</span> </v-card-text>
          <v-card-text class="grey--text mt-n4"> Payment<span style="color: orange">Method</span>  </v-card-text>
          <v-card-text class="grey--text mt-n4"> Delivery<span style="color: orange">Status</span>  </v-card-text>
          <v-card-text class="grey--text mt-n4"> <span style="color: orange">Returns</span> </v-card-text>
        </v-col>
        <v-col cols="12" xs="12" sm="6" md="4">
          <v-card-text class="white--text pt-0">
            <h3 class="heading">Contact <span style="color: orange">Us</span></h3>
          </v-card-text>
          <v-card-text class="grey--text "> Vehari,Punjab,<span style="color: orange">Pakistan</span> </v-card-text>
          <v-card-text class="mt-n4" style="color: orange">hamid313500@gmail.com </v-card-text>
          <v-card-text class="grey--text mt-n4">
            +92 319-<span style="color: orange">7286163</span>
          </v-card-text>
          <v-card-text class="grey--text mt-n4"> +92 321-<span style="color: orange">9326163</span> </v-card-text>
        </v-col>
      </v-row>
      <div class="copy">
        <h3 style="color: orange" >CopyRight@2024 | All rights reserved.</h3>
      </div>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  data: () => ({

  }),
};
</script>

<style>
.copy{
  color: grey;
    text-align: center;
    margin-bottom: -2rem;
    margin-top: 2rem;
    border-top: 1px solid orange;
}
.copy h3{
  margin-top: 1rem;
}
.footer {
  background-color: rgb(39, 38, 38);
}

.icon {
  display: flex;
}

.heading {
  color: white;
}

.green--text {
  color: green !important;
}

.grey--text {
  color: gray !important;
}
</style>