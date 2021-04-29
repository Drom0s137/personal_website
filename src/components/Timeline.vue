<template>
	<div>
		<v-dialog v-model="show" scrollable max-width="800px">
			<v-card>
				<v-card-title class="text-h3">
					Timeline
					<v-btn icon class="ml-auto" @click="show=false">
						<v-icon large>mdi-close</v-icon>
					</v-btn>
				</v-card-title>
				<v-divider />
				<v-card-text class="py-0 pl-0 px-sm-5">
					<v-timeline :dense="$vuetify.breakpoint.xsOnly" scrollable align-top>
						<v-timeline-item
							v-for="event in landmarks"
							:key="event.title"
							:icon="(event.rawDate < new Date()) ? 'mdi-check' : ''"
							:color="(event.rawDate < new Date()) ? 'red darken-4' : 'blue'"
						>
							<!-- :icon="completed ? 'mdi-check' : ''" -->
							<span slot="opposite">{{event.date}}</span>
							<v-card elevation="10" :color="(event.rawDate < new Date()) ? 'red darken-4' : 'blue'">
								<v-card-title class="headline white--text" style="word-break:normal">{{event.title}}</v-card-title>
								<v-card-subtitle class="hidden-sm-and-up white--text">{{event.date}}</v-card-subtitle>
								<v-card-text class="white pt-3">{{event.text}}</v-card-text>
								<v-sheet v-if="event.link" color="white">
									<v-btn
										v-if="event.title === 'Info Session 1'"
										class="mx-4 mb-3 mt-n3 red darken-4"
										dark
										:href="event.link"
										target="_blank"
									>Recording</v-btn>
									<v-btn
										v-if="event.title === 'Info Session 2'"
										class="mx-4 mb-3 mt-n3 red darken-4"
										dark
										:href="event.link"
										target="_blank"
									>Presentation</v-btn>
									<v-btn
										v-if="event.title === 'Advanced Info Session'"
										class="mx-4 mb-3 mt-n3 red darken-4"
										dark
										:href="event.link"
										target="_blank"
									>Presentation</v-btn>
									<v-btn
										v-if="event.title === 'Beginner Info Session'"
										class="mx-4 mb-3 mt-n3 red darken-4"
										dark
										:href="event.link"
										target="_blank"
									>Presentation</v-btn>
									<v-btn
										v-if="event.title.substr(0, event.title.indexOf(' ')) === 'Workshop'"
										class="mx-4 mb-3 mt-n3"
										:color="(event.rawDate < new Date()) ? 'red darken-4' : 'blue'"
										dark
										:href="event.link"
										target="_blank"
									>Workshop</v-btn>
									<v-btn
										v-if="event.title === 'Final Info Session'"
										class="mx-4 mb-3 mt-n3 red darken-4"
										dark
										:href="event.link"
										target="_blank"
									>Recording</v-btn>
								</v-sheet>
							</v-card>
						</v-timeline-item>
					</v-timeline>
				</v-card-text>
			</v-card>
		</v-dialog>
	</div>
</template>

<script>
export default {
	props: { value: Boolean },
	data() {
		return {
			landmarks: [
				{
					title: "Final Info Session",
					date: "March 3",
					rawDate: new Date("March 3, 2021"),
					text: "Final details on Showcase",
					link:
						"https://web.microsoftstream.com/video/9773b2aa-fb0d-48d2-a200-ef991f344d28",
				},
				{
					title: "Workshop 5",
					date: "March 16",
					rawDate: new Date("March 16, 2021"),
					text: "Workshop for CAD",
					link: "https://sumobot.ca/#/workshop",
				},
				{
					title: "Showcase",
					date: "April 3rd",
					rawDate: new Date("April 30, 2021"),
					text: "Show off your bot at last!",
				},
				{
					title: "Info Session 1",
					date: "15 September",
					rawDate: new Date("September 15, 2020"),
					text:
						"Our first informal info session, click here to watch the recording!",
					link: "https://www.instagram.com/p/CFLE7fXqSVl/",
				},
				{
					title: "Info Session 2",
					date: "25 September",
					rawDate: new Date("September 25, 2020"),
					text:
						"Our first formal info session, with finalised details for the winter!",
					link: "/InfoSession.pdf",
				},
				{
					title: "Advanced Info Session",
					date: "10 October",
					rawDate: new Date("October 10, 2020"),
					text:
						"Details about the advanced competition, its rules and more information!",
					link: "/Advanced_Competition.pdf",
				},
				{
					title: "Beginner Info Session",
					date: "24 October",
					rawDate: new Date("October 25, 2020"),
					text:
						"More details about the rules and the competition details for the beginner competition",
					link: "/Beginner_Competition.pdf",
				},
				{
					title: "Workshop 1",
					date: "November 9, 6:30pm",
					rawDate: new Date("November 9, 2020"),
					text: "Workshop for Arduino and programming",
					link: "https://sumobot.ca/#/workshop",
				},
				{
					title: "Workshop 2",
					date: "November 19, 6:30pm",
					rawDate: new Date("November 19, 2020"),
					text: "Workshop for Motors and Deisgn",
					link: "https://sumobot.ca/#/workshop",
				},
				{
					title: "Workshop 3",
					date: "November 28, 5:30pm",
					rawDate: new Date("November 28, 2020"),
					text: "Workshop for Sensors",
					link: "https://sumobot.ca/#/workshop",
				},
				{
					title: "Workshop 4",
					date: "March 12",
					rawDate: new Date("March 12, 2021"),
					text: "Workshop for Sensors",
					link: "https://sumobot.ca/#/workshop",
				},
			],
		};
	},
	computed: {
		show: {
			get() {
				return this.value;
			},
			set(value) {
				this.$emit("input", value);
			},
		},
	},
};
</script>