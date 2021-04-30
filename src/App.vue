<template>
  <v-app>
    <!-- NavBar -->
    <v-app-bar app :class="scrlpoint ? 'scrlpoint' : 'scrl0'" short>
      <!--<router-link to="/" class="logo" tag="img" :src="scrlpoint ? logob : logow" />
      <router-link
        to="/"
        tag="h1"
        style="cursor:pointer"
        :class="scrlpoint ? '' : 'white--text font-weight-regular'"
        v-if="$vuetify.breakpoint.mdAndUp || $vuetify.breakpoint.xsOnly"
      >Sumobotfdasf</router-link> -->
      <!-- <h1
				style="cursor:pointer"
				@click.stop=""
				:class="scrlpoint ? '' : 'white--text font-weight-regular'"
				v-if="$vuetify.breakpoint.mdAndUp || $vuetify.breakpoint.xsOnly"
			>
				Sumobot
      </h1>-->
      <v-app-bar-nav-icon @click="menu = !menu" class="ml-auto mr-2 d-sm-none" />
      <!-- Menu -->
      <span class="ml-auto mr-4 d-none d-sm-flex">
        <v-btn text to="/">HOME</v-btn>
        <v-btn text to="/workshop">PROJECTS</v-btn>
        <v-btn text to="/about">EXPERIENCE</v-btn>
        <v-btn text @click.stop="partshow = true"><Parts /></v-btn>
      </span>
      <!-- Menu -->
    </v-app-bar>
    <!-- NavBar -->
    <!-- Mobile Menu -->
    <v-bottom-navigation
      app
      :input-value="menu"
      scroll-threshold="50"
      hide-on-scroll
      :color="intersect ? '' : 'red darken-4'"
      :dark="intersect"
      :background-color="intersect ? '#9a2a29' : ''"
      v-if="$vuetify.breakpoint.xsOnly"
      height="90px"
    >
      <v-btn to="/">
        <span>Home</span>
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-btn to="/about">
        <span>About</span>
        <v-icon>mdi-information-outline</v-icon>
      </v-btn>
      <v-btn to="/workshop">
        <span>Workshop</span>
        <v-icon>mdi-book</v-icon>
      </v-btn>
      <v-btn @click.stop="showtimeline = true">
        <span>Timeline</span>
        <v-icon>mdi-clock</v-icon>
      </v-btn>
      
    </v-bottom-navigation>
    <!-- Mobile Menu -->
    <!-- Page Views -->
    <v-main class="pa-0">
      <router-view />
    </v-main>
    <!-- Page Views -->
    <!-- Footer -->
    <v-footer dark color="#9a2a29" class="py-0">
      <!-- Width makes sheet full size, removing causes issues -->
      <!-- Padding needed for mobile view, when menu present -->
      <v-sheet color="#9a2a29" width="100%" :class="menu ? 'pb-10 pb-sm-0' : ''">
        <!-- Row allows columns to switch in mobile view -->
        <v-row justify="center" class="text-center py-2 py-sm-6">
          <!-- Conatct Column -->
          <v-col cols="12" sm="4" lg="2">
            <span
              class="d-flex align-center justify-center text-h5 font-weight-medium mb-3 mb-sm-6"
            >
              <v-icon size="28" class="pr-2">mdi-email</v-icon>CONTACT
            </span>
            Email me at:
            <br />
            <a
              href="mailto:eddy.che.su@gmail.com"
              target="_blank"
              style="color:white"
            >eddy.che.su@gmail.com</a>
          </v-col>
          <!-- Conatct Column -->
        </v-row>
        <v-divider />
        <!-- Name year Text -->
        <!-- Padding needed for mobile view, when menu present -->
        <v-card-text
          class="pa-2 d-flex justify-center align-center pb-10 pb-sm-2"
          :class="menu ? 'pb-16 pb-sm-2' : ''"
        >
          {{ new Date().getFullYear() }} — Eddy Su 
        </v-card-text>
        <!-- Name year Text -->
      </v-sheet>
    </v-footer>
    <!-- Footer -->
    <Timeline v-model="showtimeline" />
  </v-app>
</template>

<script>
// Images imported to use in navbar
import Parts from "./components/Parts";
export default {
  components: { Parts },
  data() {
    return {
      scrlpoint: false,
      menu: false,
      intersect: false,
      partshow: false,
      snackbar: true,
    };
  },
  methods: {
    // updateScroll checks how far page is scrolled, and changes scrlpoint value accordingly
    updateScroll() {
      window.scrollY >= 50 ? (this.scrlpoint = true) : (this.scrlpoint = false);
    },
    onIntersect(entries) {
      this.intersect = entries[0].isIntersecting;
    },
  },
  watch: {
    scrlpoint(value) {
      this.menu = value;
    },
    $route: {
      immediate: true,
      handler(to) {
        document.title = to.meta.title || "Sumobot";
      },
    },
  },
  mounted() {
    // Starts updateScroll method
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>

<style scoped>
.scrl0 {
  transition-duration: 300ms;
  background-color: transparent !important;
  box-shadow: none !important;
}
/* Makes button before scrlpoint white in colour */
.scrl0 .v-btn {
  color: #fff !important;
}
.scrlpoint {
  transition-duration: 300ms;
  background-color: #fff !important;
}
span .v-btn {
  font-weight: bolder !important;
}
/* Padding removed to make menu flush with screen edge */
.v-app-bar >>> .v-toolbar__content {
  padding: 0 !important;
}
.v-item-group >>> .v-slide-group__wrapper {
  margin-right: -10px;
  margin-left: -12px;
}
</style>

<style>
body::-webkit-scrollbar {
  background: #cfcfcf;
  border-radius: 10px;
  width: 10px;
}

body::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: #868686;
}
</style>
