<template>
	<v-container fluid py-0>
		<!-- Top row, Introduction -->
		<v-row class="row1" align="center">
			<bubble v-if="$vuetify.breakpoint.smAndDown" />
			<!-- Video for desktop screens -->
			<span
				style="background-color: rgba(40,0,0,0.5);position:absolute;height:100%;width:100%;z-index:1"
				v-if="$vuetify.breakpoint.mdAndUp"
			/>
			<video
				autoplay
				muted
				loop
				class="video"
				poster="../assets/Home/Intro.jpg"
				v-if="$vuetify.breakpoint.mdAndUp"
			>
				<source src="../assets/Home/Intro2.mp4" type="video/mp4" />
			</video>
			<!-- Video for desktop screens -->
			<v-col cols="12" class="text-center" style="z-index:2">
				<span class="toptitle d-block text-h5 font-weight-regular mb-8">Eddy Su</span>
				<span class="d-block text-h5 text-md-h3 mb-15 font-weight-regular">Dedicated Mechatronics Engineer</span>
	
				<v-btn
					x-large
					rounded
					class="font-weight-bold white--text blue mx-1 mb-3"
					href="https://github.com/Drom0s137?tab=repositories"
					target="_blank"
				>
					<v-icon class="mr-2">mdi-account-group</v-icon>Github
				</v-btn>
				<v-btn
					x-large
					rounded
					class="font-weight-bold white--text blue mx-1 mb-3"
					href="https://www.linkedin.com/in/che-su-mac/"
					target="_blank"
				>
					<v-icon class="mr-2">mdi-account-group</v-icon>Linkedin 
				</v-btn>
			</v-col>
		</v-row>
		<!-- Top row, Introduction -->
		<!-- Description of Sumobot -->
		<v-row id="whowe" class="white py-10" justify="center" align="center">
			<v-col cols="12">
				<div class="heading">About Me</div>
			</v-col>
			<v-col cols="11" md="4" order-md="1" class="mb-md-0 mb-5 mt-10">
				<v-img src="~../assets/Home/portfolio_pic.jpg" max-height="300" eager />
			</v-col>
			<v-col cols="11" md="6" order-md="0" class="px-md-10" style="font-size:1.3rem">
				<div class="mb-5 font-weight-regular">
					Hi there, my name is Eddy and I am a first year engineering student with a huge 
					interest in Computer Vision and Robot Navigation. I have explored with backend development 
					and now have a good understanding of <b> OpenCV </b> and <b> ZeroMQ </b>. 
				</div>
				<div>
					I am currently exploring the use of navigation using lidars and accelerometers 
					to create a robot capable of freely navigating a room. 
				</div>
			</v-col>
		</v-row>

		<!-- Showcase -->
		<!-- Slanted edge -->
		<!-- Slanted edge -->
		<v-sheet
			class="mx-n3 mt-10"
			style="border-bottom: 5vw solid #9a2a29; border-right: 100vw solid transparent;"
		/>
		<v-sheet
			class="mx-n3"
			style="border-top: 5vw solid #9a2a29; border-left: 100vw solid transparent;background:#eee"
		/>
		<!-- Slanted edge -->
		<!-- Competition Details -->
		<v-row class="px-sm-10 py-5" style="background-color:#eee" justify="center">
			<v-col cols="12">
				<div class="heading">Skills</div>
			</v-col>
			<!-- Beginner Card -->
			<v-col cols="11" sm="6" lg="4">
				<v-sheet rounded class="pa-5" height="100%">
					<div class="text-center text-h5 mb-5">
						Programming Languages
					</div>
					<v-row>
						<v-col cols="12" lg="5" class="py-0" order-lg="0">
							<ul class="text-subtitle-1 font-weight-medium">
								<li>C/C++</li>
								<li>Java</li>
								<li>Python</li>
								<li>Go</li>
								<li>MatLab</li>
								<li>CSS</li>
							</ul>
						</v-col>
					</v-row>
				</v-sheet>
			</v-col>
			<!-- Beginner Card -->
			<!-- Advanced Card -->
			<v-col cols="11" sm="6" lg="4">
				<v-sheet rounded class="pa-5" height="100%">
					<div class="text-center text-h5 mb-5">
						Programming Libraries
					</div>
					<v-row>
						<v-col cols="12" lg="7" class="py-0" order-lg="0">
							<ul class="text-subtitle-1 font-weight-medium">
								<li>Numpy</li>
								<li>Matplotlib</li>
								<li>OpenCV</li>
								<li>Pysot</li>
								<li>OpenPose</li>
							</ul>
						</v-col>
					</v-row>
				</v-sheet>
			</v-col>
			<!-- Advanced Card -->
			<!-- Advanced Card -->
			<v-col cols="11" sm="6" lg="4">
				<v-sheet rounded class="pa-5" height="100%">
					<div class="text-center text-h5 mb-5">
						CAD
					</div>
					<v-row>
						<v-col cols="12" lg="7" class="py-0" order-lg="0">
							<ul class="text-subtitle-1 font-weight-medium">
								<li>EagleCAD</li>
								<li>Inventor</li>
								<li>Solidworks</li>
							</ul>
						</v-col>
					</v-row>
				</v-sheet>
			</v-col>
			<!-- Advanced Card -->
			
		</v-row>
		<!-- Competition Details -->
	</v-container>
</template>

<script>
import bubble from "../assets/bubble";

export default {
	components: { bubble },
	data() {
		return {
			orderdialog: false,
		};
	},
	methods: {
      randomValue() {
        this.value = Math.random() * this.max
      }
    }
};
</script>

<style scoped>
.row1 {
	/* Adding a gradient over image to make text slightly more legible */
	background-image: linear-gradient(rgba(226, 19, 19, 0.1), rgba(39, 0, 0, 0.4)),
		url("../assets/Home/Intro.jpg");
	background-size: cover;
	background-position-x: 40%;
	height: 50vh;
	color: white;
	position: relative;
}
.video {
	z-index: 0;
	position: absolute;
	object-fit: cover;
	right: 0;
	bottom: 0;
	width: 100%;
	height: 100%;
}
.heading {
	width: fit-content;
	margin: 0 auto;
	font-size: 36px;
	font-weight: bold;
	padding: 0 4vw;
	border-bottom: solid 2px #9a2a29;
}
li {
	list-style: none;
	position: relative;
}
li:before {
	content: "\2022";
	position: absolute;
	left: -1em;
	color: #9a2a29;
	font-weight: 900;
}
.innerlist >>> li:before {
	content: "\25b8";
	color: black;
}

/* Switch toptitle style at 700px */
@media (min-width: 700px) {
	.toptitle {
		font-size: 10vw !important;
		margin-bottom: 5vw !important;
		margin-top: 80px;
	}
}
</style>
