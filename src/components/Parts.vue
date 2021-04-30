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
			<v-col cols="12" md="11" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Projects/resume.jpg" max-height="100vh" eager />
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
    };
  },
};
</script>
