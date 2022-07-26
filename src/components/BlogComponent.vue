<template>
	<section class="section section--blog">
		<div class="section__header">
			<h2 class="heading heading--sec">Latest Articles</h2>
		</div>
		<div class="section__content">
			<blog-posts 
			v-for="blog in blogPosts"
			:key="blog.id"
			:image="blog.image"
			:alt="blog.alt"
			:writerName="blog.writerName"
			:header="blog.header"
			:link="blog.link"
			:lead="blog.lead"
			/>
		</div>
	</section>
</template>

<script>
import BlogPosts from "./BlogPosts.vue";
export default {
	components: {
		BlogPosts,
	},
	data() {
		return {
			blogPosts: [
				{
					id: 0,
					image: "image-currency.jpg",
					alt: "image of some currencies",
					writerName: "By Claire Robinson",
					link: "#",
					header: "Receive money in any currency with no fees",
					lead: "The world is getting smaller and we’re becoming more mobile. So why should you be forced to only receive money in a single…"
				},
				{
					id: 1,
					image: "image-restaurant.jpg",
					alt: "an image of some dishes on a table in a resurant",
					writerName: "By Wilson Hutton",
					link: "#",
					header: "Treat yourself without worrying about money",
					lead: "Our simple budgeting feature allows you to separate out your spending and set realistic limits each month. That means you…"
				},
				{
					id: 2,
					image: "image-plane.jpg",
					alt: "an image of the wing of an airplane in the sky",
					writerName: "By Wilson Hutton",
					link: "#",
					header: "Take your Easybank card wherever you go",
					lead: "We want you to enjoy your travels. This is why we don’t charge any fees on purchases while you’re abroad. We’ll even show you…"
				},
				{
					id: 3,
					image: "image-confetti.jpg",
					alt: "an image of image-confetti in the air",
					writerName: "By Claire Robinson",
					link: "#",
					header: "Our invite-only Beta accounts are now live!",
					lead: "After a lot of hard work by the whole team, we’re excited to launch our closed beta. It’s easy to request an invite through the site..."
				},
			]
		}
	}
};
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";
.section--blog {
	background-color: var(--VeryLightGray);
}
</style>
