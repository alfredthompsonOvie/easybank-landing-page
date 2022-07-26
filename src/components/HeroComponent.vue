<template>
	<section class="hero">
		<div class="hero__graphics">
			<img
				src="@/assets/image-mockups.png"
				alt="an image showing how Easybank looks on mobile phones"
				class="hero__img"
			/>
		</div>
		<div class="hero__content">
			<h1 class="heading heading--hero">Next generation digital banking</h1>
			<p class="description description--default">
				Take your financial life online. Your Easybank account will be a
				one-stop-shop for spending, saving, budgeting, investing, and much more.
			</p>
			<a href="#" class="cta cta--default cta--hero">Request Invite</a>
		</div>
	</section>
</template>

<script>
export default {
	name: "HeroComponent",
};
</script>

<style lang="scss" scoped>
@import '../scss/main.scss';

.hero {
	display: grid;
	grid-template-columns: 0.1fr 1.8fr 0.1fr;
	grid-template-rows: auto auto;
	position: relative;
	padding-bottom: 5em;
	background-color: var(--VeryLightGray);
	z-index: 6;
	/* ----------------------- */
	@media (min-width: 992px) {
		display: grid;
		grid-template-columns: 0.1fr 1fr 1fr 0.1fr;
		grid-template-rows: 75vh;
		grid-template-rows: 500px;
		z-index: 6;
		padding-bottom: 0;
	}
	@media (min-width: 1300px) {
		grid-template-columns: 0.2fr 0.8fr 0.8fr 0.2fr;
		grid-template-columns: 0.15fr 0.85fr 0.85fr 0.15fr;
	}
	@media (min-width: 1400px) {
		grid-template-columns: 0.2fr 0.8fr 0.8fr 0.2fr;
	}
}
.hero__graphics {
	grid-column: 1/-1;
	grid-row: 1;
	width: 100%;
	padding: 20em 1em 0;
	background-image: url(@/assets/bg-intro-mobile.svg);
	background-size: cover;
	background-position: right;
	background-repeat: no-repeat;
	z-index: 1;

	@media (min-width: 992px) {
		grid-column: 3/-1;
		grid-row: 1;
		background-image: url(@/assets/bg-intro-desktop.svg);
		background-position: top -9.7em left -2em;
		background-size: 50em;
		padding: 0;
		position: relative;
		z-index: 1;
	}
}
.hero__img {
	position: absolute;
	top: -6.5em;
	left: 0;
	right: 0;
	max-width: 384px;
	width: 100%;
	@media (min-width: 400px) {
		max-width: 400px;
		margin-inline: auto;
	}
	@media (min-width: 992px) {
		top: -4.5em;
		right: -6em;
		left: initial;
		max-width: initial;
		width: 530px;
	}
	@media (min-width: 1200px) {
		width: 550px;
	}
}
.hero__content {
	grid-column: 2;
	grid-row: 2;
	text-align: center;
	padding-top: 1em;
	@media (min-width: 440px) {
		margin-top: 2em;
		padding-top: 1.5em;
	}
	@media (min-width: 992px) {
		margin-top: 0em;
		/* padding-top: 0; */

		grid-column: 2;
		grid-row: 1;
		text-align: left;
		padding-top: 1em;
		align-self: center;
	}
}

.heading--hero {
	font-size: clamp(2rem, 9vw, 2.5rem);
	@media (min-width: 992px) {
		font-size: clamp(3rem, 5vw, 3.5rem);
	}
}
/* ------------------ */
</style>
