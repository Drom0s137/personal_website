<template>
	<v-container fluid py-0>
		<v-row class="row1" align="center">
			<v-col class="text-center">
				<span class="d-block text-h2 text-sm-h1 font-weight-regular mb-8">Projects</span>
				<span
					class="d-block text-h5 text-md-h4 mb-10 font-weight-regular"
				>Hands on experience from project-based learning</span>
				
			</v-col>
		</v-row>
		<v-row class="ma-3 mx-md-16" id="tutorial">
			<v-col cols="12" md="6" class="d-flex text-center align-center justify-center px-sm-10">
				<span>
					<h2 style="color:#9a2a29">Project V.A.R.I.S</h2>
					<p>
						<b>Autonomous home assistance robot currently under development </b>
						<br />The develoopment of this robot is intended for assisting eldelied on basic tasks such
						as picking fallen objects up from the floor and act as a security camera. This robot will be
						imbeded with lidar navigation and computer vision tools to create a user-friendly experience. 
					</p>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href=""
						target="_blank"
					>More information coming up soon</v-btn>
				</span>
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Projects/varis.jpg" max-height="45vh" eager />
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Projects/vc_arm.jpg" max-height="45vh" eager />
			</v-col>
			<v-col cols="12" md="6" class="d-flex text-center align-center justify-center px-sm-10">
				<span>
					<h2 style="color:#9a2a29">Voice-controlled Robot Arm</h2>
					<p>
						3D printed robot arm controlled using Arudino and BitVoicer.
					</p>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href="https://github.com/Drom0s137/voice_controlled_robot_arm"
						target="_blank"
					>Github Repository</v-btn>
				</span>
			</v-col>
			<v-col cols="12" md="6" class="d-flex text-center align-center justify-center px-sm-10">
				<span>
					<h2 style="color:#9a2a29">Low Voltage System</h2>
					<p>
						Different sensors serve different purposes
						<br />Find out which ones suit your needs!
					</p>
					<v-btn class="red darken-4 ma-2 white--text"
						href="/lv.pdf"
						target="_blank"
					>Schematics</v-btn>
				</span>
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Projects/lv.jpg" max-height="60vh" eager />
			</v-col>
			
		</v-row>
	</v-container>
</template>

<script>
export default {
	data() {
		return {};
	},
};
</script>

<style scoped>
.landing-page-buttons {
	display: flex;
	flex-direction: column;
	align-items: center;
}

.row1 {
	/* Adding a gradient over image to make text slightly more legible */
	background-image: linear-gradient(rgb(154 42 41 / 50%), rgb(154 42 41 / 50%)),
		url("~../assets/Projects/Aeroshell Design.jpg");
	background-size: cover;
	background-position-x: 60%;
	height: 50vh;
	color: white;
}
</style>
