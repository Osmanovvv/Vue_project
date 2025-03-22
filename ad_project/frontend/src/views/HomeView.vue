<template>
  <v-container>
    <!-- Карусель для промо-объявлений -->
    <v-row justify="center">
      <v-col cols="12" xs="12">
        <v-carousel>
          <v-carousel-item
            v-for="ad in ads"
            :key="ad.id"
            :src="ad.src"
            :alt="ad.title"
            cover
          >
            <v-card class="pa-3">
              <v-card-title>{{ ad.title }}</v-card-title>
              <v-card-subtitle>{{ ad.desc }}</v-card-subtitle>
            </v-card>
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>

    <!-- Карточки для всех объявлений -->
    <v-row justify="center">
      <v-col v-for="ad in ads" :key="ad.id" cols="12" sm="6" lg="4">
        <v-card>
          <v-img :src="ad.src" height="200px"></v-img>
          <v-card-title>{{ ad.title }}</v-card-title>
          <v-card-subtitle>{{ ad.desc }}</v-card-subtitle>
          <v-card-actions>
            <v-btn text>Details</v-btn>
            <v-btn raised color="primary">Buy</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      ads: [
        {
          title: "First",
          desc: "First Desc",
          promo: true,
          src: "https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg",
          id: "1"
        },
        {
          title: "Second",
          desc: "Second Desc",
          promo: true,
          src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg",
          id: "2"
        },
        {
          title: "Third",
          desc: "Third Desc",
          promo: true,
          src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg",
          id: "3"
        },
        {
          title: "Fourth",
          desc: "Fourth Desc",
          promo: true,
          src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg",
          id: "4"
        }
      ]
    };
  }
};
</script>
