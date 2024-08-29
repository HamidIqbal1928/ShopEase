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
          bio: "I had a fantastic experience buying this smart watch online. The website is incredibly user-friendly and visually appealing. The product selection is impressive, with detailed descriptions and reviews. The purchasing process was smooth, and the customer service was top-notch—responsive and helpful with recommendations. Overall, it was a great online shopping experience!",
        },
        {
          img: p2,
          title: "Muhammad Numan",
          subtitle: "Full stack Developer",
          bio: "I had a wonderful experience buying my new mobile phone online. The site is easy to use and offers a fantastic range of options. The mobile I purchased is fantastic and exactly what I was looking for. The customer service was exceptional—quick to respond and very helpful with recommendations. Overall, it was a smooth and satisfying shopping experience, and I’ll definitely return for future tech needs!",
        },
        {
          img: p3,
          title: "Aziz-ur-Rehman",
          subtitle: "Backend Developer",
          bio: "“I had an excellent experience buying my laptop online. The website is easy to navigate and offers a great selection of products. The laptop I purchased exceeded my expectations in performance and quality. The customer service was outstanding—helpful and attentive throughout the process. Overall, it was a fantastic and I'll definitely consider this site for future tech purchases!”",
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
