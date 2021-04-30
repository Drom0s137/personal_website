<template>
  <v-container fluid py-0>
    <v-row class="row1" align="center">
      <v-col class="text-center">
        <span class="toptitle d-block text-h2 font-weight-regular mb-8">Experience</span>
      </v-col>
    </v-row>
    <v-timeline
    align-top
    :dense="$vuetify.breakpoint.smAndDown"
  >
    <v-timeline-item
      v-for="(item, i) in items"
      :key="i"
      :color="item.color"
      :icon="item.icon"
      fill-dot
    >
      <v-card
        :color="item.color"
        dark
      >
        <v-card-title class="title">
          {{item.title}}
        </v-card-title>
        <v-card-text class="white text--primary">
          <p>{{item.description}}</p>
 
        </v-card-text>
        
      </v-card>
      
    </v-timeline-item>
  </v-timeline>
  </v-container>


</template>

<script>
  export default {
    data: () => ({
      items: [
        {
          color: 'red lighten-2',
          icon: 'mdi-star',
          title: 'Software Engineer at ARVI',
          description: 'Maintained backend code on camera based tracking product: AXIBO',
        },
        {
          color: 'purple darken-1',
          icon: 'mdi-book-variant',
          title: 'Project Manager at McMaster Solar Car Project',
          description: 'Lead a team of 50 to develop and create a fully solar powered vehicle to participate in the American Solar Challenge, product currently in construction.',
        },
        {
          color: 'green lighten-1',
          icon: 'mdi-airballoon',
          title: 'Backend Deveoper at ARVI',
          description: 'Integrated a computer vision tracker to the backend using C++ and python to a camera product: AXIBO. Performed testing on various computer vision tracking solutions by creating a scoring system on the deviation from ground truth. ',
        },
        {
          color: 'blue lighten-1',
          icon: 'mdi-airballoon',
          title: 'Cheif Technology Officer at McMaster Makers',
          description: 'Lead a team of engineering students to learn and develop workshops to educated students around campus on engineering topics such as html, OpenCV, SQL databases, Android Studio, etc. ',
        },
        {
          color: 'pink lighten-1',
          icon: 'mdi-airballoon',
          title: 'President of McMaster Sumobot',
          description: 'Lead a club to create campus-wide Sumobot competitions and created workshops on Arduino, sensors, and Inventor to help students with no prior knowledge,',
        },
        {
          color: 'green lighten-1',
          icon: 'mdi-airballoon',
          title: 'Summer Research Student at McMaster Univerisuty',
          description: 'Created Labs and conducted research on the use of node-red, TCP/UDP sockets, RabbitMQ, ZeroMQ, Redis as well as centroid Tracking/Motion Detection/Object Tracking using OpenCV',
        },
        {
          color: 'purple lighten-1',
          icon: 'mdi-airballoon',
          title: 'Community Solutions Developer at MacChangers',
          description: 'Gained knowledge on the importance and methods of problem identification aimed at developing engineering solutions for Hamilton HSR.',
        },
      ],
    }),
  }
</script>

<style>
.row1 {
  /* Adding a gradient over image to make text slightly more legible */
  background-image: linear-gradient(rgb(154 42 41 / 50%), rgb(154 42 41 / 50%)),
    url("../assets/About/axibo.jpg");
  background-size: cover;
  background-position-y: 80%;
  background-position-x: 30%;
  height: 50vh;
  color: white;
  position: relative;
}
.titleblock {
  width: fit-content;
  margin: 0 auto;
  font-size: 36px;
  font-weight: bold;
  padding: 0 4vw;
  border-bottom: solid 2px #9a2a29;
}

.hov:hover {
  cursor: pointer;
  transition-duration: 0.3s;
  transform: translateY(-2%);
}
.v-dialog.v-dialog--active {
  margin: 0px !important;
}
</style>
