<template>
		<main>
			<hero-component />
			<about-component />
			<blog-component />
		</main>
		<footer-component />
</template>

<script>
import HeroComponent from "@/components/HeroComponent.vue";
import AboutComponent from "@/components/AboutComponent.vue";
import BlogComponent from "@/components/BlogComponent.vue";
import FooterComponent from "@/components/FooterComponent.vue";

export default {
	name: "HomeView",
	components: {
		HeroComponent,
		AboutComponent,
		BlogComponent,
		FooterComponent,
	},
};
</script>
<style lang="scss" scoped>
@import "../scss/main.scss";
</style>
