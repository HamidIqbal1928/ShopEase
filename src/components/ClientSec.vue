<template>
  <v-row class="mt-10 mb-5" id="client" justify="center">
    <v-col
      cols="12"
      xs="12"
      sm="6" 
      md="4"
      lg="3" 
      v-for="(client, i) in clients"
      :key="i"
    >
      <v-card class="elevation-16 mx-auto" id="pic" max-width="300px"> <!-- Added max-width -->
        <v-list subheader two-line>
          <v-list-item>
            <v-list-item-avatar>
              <v-img :src="client.img"></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title class="title">{{ client.title }}</v-list-item-title>
              <v-list-item-subtitle class="subtitle">{{ client.subtitle }}</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-card-text>
          <div class="mt-n7 rating">
            <v-rating
              v-model="rating"
              class="custom-rating"
              color="yellow darken-3"
              background-color="grey darken-1"
              empty-icon="$ratingFull"
              half-increments
              hover
              small
            ></v-rating>
          </div>
          {{ client.bio }}
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import p1 from '../assests/hamid.png';
import p2 from '../assests/noman.png';
import p3 from '../assests/Azizo.png';
export default {
  data: () => ({
    rating: 4.5,
    clients: [
      {
        img: p1,
        title: "Hamid Iqbal",
        subtitle: "Frontend Developer",
        bio: "“It’s a great experience. The ambiance is very welcoming and charming. Amazing wines, food, and service. Staff are extremely knowledgeable and make great recommendations.”",
      },
      {
        img: p2,
        title: "Muhammad Numan",
        subtitle: "Full stack Developer",
        bio: "It’s the cutest little spot with amazing food. The Pizza is to die for. IT WAS FIRE!! The service we received was so amazing, and we will definitely be back again. They made us happy",
      },
      {
        img: p3,
        title: "Aziz-ur-Rehman",
        subtitle: "Backend Developer",
        bio: "“This place is great! The atmosphere is chill and cool, but the staff is also really friendly. They know what they’re doing and what they’re talking about, and you can tell making the customers happy.”",
      },
    ],
  }),
};
</script>

<style>
.title{
  color: rgb(196, 86, 46);
}
#pic {
  margin: 0 auto; /* Center the card */
}
.subtitle {
  text-align: center;
}
.custom-rating .v-rating__item {
  margin: 0 -11px; /* Adjust the margin value as needed */
}
.rating {
  display: flex;
  justify-content: center; /* Center the rating */
}
</style>
