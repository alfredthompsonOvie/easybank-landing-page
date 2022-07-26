<template>
	<section class="section section--about">
		<div class="section__header">
			<h2 class="heading heading--sec">Why choose Easybank?</h2>
			<p class="description description--about">
				We leverage Open Banking to turn your bank account into your financial
				hub. Control your finances like never before.
			</p>
		</div>
		<div class="section__content">
			<!-- <div class="card card--about">
				<img
					src="@/assets/icon-online.svg"
					alt="an icon of online banking"
					class="card--icon"
				/>
				<div class="card__content">
					<h4 class="card__header">Online Banking</h4>
					<p class="description description--about-card">
						Our modern web and mobile applications allow you to keep track of
						your finances wherever you are in the world.
					</p>
				</div>
			</div>
			<div class="card card--about">
				<img
					src="@/assets/icon-budgeting.svg"
					alt="a budget icon"
					class="card--icon"
				/>
				<div class="card__content">
					<h4 class="card__header">Simple Budgeting</h4>
					<p class="description description--about-card">
						See exactly where your money goes each month. Receive notifications
						when you’re close to hitting your limits.
					</p>
				</div>
			</div>
			<div class="card card--about">
				<img
					src="@/assets/icon-onboarding.svg"
					alt="an onboarding icon"
					class="card--icon"
				/>
				<div class="card__content">
					<h4 class="card__header">Fast Onboarding</h4>
					<p class="description description--about-card">
						We don’t do branches. Open your account in minutes online and start
						taking control of your finances right away.
					</p>
				</div>
			</div>
			<div class="card card--about">
				<img src="@/assets/icon-api.svg" alt="an api icon" class="card--icon" />
				<div class="card__content">
					<h4 class="card__header">Open API</h4>
					<p class="description description--about-card">
						Manage your savings, investments, pension, and much more from one
						account. Tracking your money has never been easier.
					</p>
				</div>
			</div> -->
			<features-card v-for="feature in features"
			:key="feature.id"
			:image="feature.image"
			:alt="feature.alt"
			:header="feature.header"
			:description="feature.description"
			class="card card--about"
			/>
		</div>
	</section>
</template>

<script>
import FeaturesCard from "./FeatureCard.vue";
export default {
	components: {
		FeaturesCard,
	},
	data() {
		return {
			features: [
				{
					id: 0,
					image: "icon-online.svg",
					alt: "an icon of online banking",
					header: "Online Banking",
					description: "Our modern web and mobile applications allow you to keep track of your finances wherever you are in the world."
				},
				{
					id: 1,
					image: "icon-budgeting.svg",
					alt: "a budget icon",
					header: "Simple Budgeting",
					description: "See exactly where your money goes each month. Receive notifications when you’re close to hitting your limits."
				},
				{
					id: 2,
					image: "icon-onboarding.svg",
					alt: "an onboarding icon",
					header: "Fast Onboarding",
					description: "We don’t do branches. Open your account in minutes online and start taking control of your finances right away."
				},
				{
					id: 3,
					image: "icon-api.svg",
					alt: "an api icon",
					header: "Open API",
					description: "Manage your savings, investments, pension, and much more from one account. Tracking your money has never been easier."
				},
			]
		}
	}
};
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";
.section--about {
	background-color: var(--LightGrayishBlue);
}

.description--about {
	margin: 1em auto 1.5em;
	max-width: 550px;
	font-size: .9rem;
	@media (min-width: 949px){
		margin-inline: 0;
	}
}
@media (min-width: 992px) {

  .description--about {
		margin: 1em 0 1.5em;
	}
}
</style>
