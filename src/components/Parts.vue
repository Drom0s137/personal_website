<template>
  <div>
    <v-btn
      class="ml-auto mr-4 d-none d-sm-flex"
      @click.stop="partshow = true"
    >Resume</v-btn>

    <v-dialog v-model="partshow" scrollable max-width="800px">
      <v-card>
        <v-card-title class="text-sm-h3 text-h4 my-2">
          Resume
          <v-btn icon class="ml-auto" @click="partshow = false">
            <v-icon large>mdi-close</v-icon>
          </v-btn>

        </v-card-title>
        <v-divider />
        <v-card-text class="py-0">
          <v-row>
            <span>
            <v-col cols="12" sm="6" v-for="item in parts" :key="item.name">
              <v-sheet class="d-flex text-center text-h5">{{item.name}}</v-sheet>
              <span>{{item.desc}}</span>

              <v-img max-height="20vh" src="require(`../assets/Home/Intro.jpg`)" class="mx-auto my-4 d-flex d-md-none" eager/>              
              </v-col>
              </span>
              </v-row>
        </v-card-text>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      partshow: false,
      parts: [
        { name: "9V - Barrel", desc: "9V connecter to power uno" }
      ]
    };
  },
};
</script>
