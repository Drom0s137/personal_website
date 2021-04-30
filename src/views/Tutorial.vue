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
					<h2 style="color:#9a2a29">Workshop 1: Arduino & Programming</h2>
					<v-img
						src="~../assets/Tutorial/Arduino.jpg"
						max-height="300px"
						max-width="80vw"
						class="mx-auto my-4 d-flex d-md-none"
						eager
					/>
					<p>
						An easy-to-use open-source platform
						<br />Tell your board what to do by loading a set of instructions to
						the microcontroller!
					</p>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href="https://web.microsoftstream.com/video/9c1ee5db-925e-48a8-983e-ea19e6fb3234"
						target="_blank"
					>Recording</v-btn>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href="/Workshop1_Arduino.pdf"
						target="_blank"
					>Presentation</v-btn>
				</span>
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Tutorial/Arduino.jpg" max-height="45vh" eager />
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Tutorial/Motor.jpg" max-height="45vh" eager />
			</v-col>
			<v-col cols="12" md="6" class="d-flex text-center align-center justify-center px-sm-10">
				<span>
					<h2 style="color:#9a2a29">Workshop 2: Motors & Design</h2>
					<v-img
						src="~../assets/Tutorial/Motor.jpg"
						max-height="300px"
						max-width="80vw"
						class="mx-auto my-4 d-flex d-md-none"
						eager
					/>
					<p>
						Learn how to configure your motors to work properly
						<br />Find out how to design the chassis effectively!
					</p>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href="https://web.microsoftstream.com/video/73de1269-114c-4e2f-bf25-9cd402bd15f3"
						target="_blank"
					>Recording</v-btn>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href="/Workshop2_Motors.pdf"
						target="_blank"
					>Presentation</v-btn>
				</span>
			</v-col>
			<v-col cols="12" md="6" class="d-flex text-center align-center justify-center px-sm-10">
				<span>
					<h2 style="color:#9a2a29">Workshop 3 & 4: Sensors</h2>
					<v-img
						src="~../assets/Tutorial/wiring.jpg"
						max-height="300px"
						max-width="80vw"
						class="mx-auto my-4 d-flex d-md-none"
						eager
					/>
					<p>
						Different sensors serve different purposes
						<br />Find out which ones suit your needs!
					</p>
					<v-btn
						class="red darken-4 mx-2 white--text"
						href="/Workshop3_Sensors.pdf"
						target="_blank"
					>Presentation</v-btn>
					<v-btn class="red darken-4 mx-2 white--text" href="/Line.ino" download>Code</v-btn>
					<v-btn class="red darken-4 ma-2 white--text"
						href="https://web.microsoftstream.com/video/d48ce5bf-a94e-47e3-af92-f00e603f85ab"
						target="_blank"
					>Recording</v-btn>
				</span>
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Tutorial/wiring.jpg" max-height="45vh" eager />
			</v-col>
			<v-col cols="12" md="6" class="pa-0 d-none d-md-flex">
				<v-img src="~../assets/Tutorial/CAD.jpg" max-height="45vh" eager />
			</v-col>
			<v-col cols="12" md="6" class="d-flex text-center align-center justify-center px-sm-10">
				<span>
					<h2 style="color:#9a2a29">Workshop 5: CAD</h2>
					<v-img
						src="~../assets/Tutorial/CAD.jpg"
						max-height="300px"
						max-width="80vw"
						class="mx-auto my-4 d-flex d-md-none"
						eager
					/>
					<p>
						Learn to design a 3D model for your robot chassis and reviewing your
						bot to make sure everything works fine!
					</p>
					<v-btn disabled class="ml-5 white--text">Recording - March 16</v-btn>
				</span>
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
		url("~../assets/Tutorial/Tutorial-intro.jpg");
	background-size: cover;
	height: 50vh;
	color: white;
}
</style>
