<template>
  <div class="card">
				<img
					:src="require(`../assets/${image}`)"
					:alt="alt"
					class="card--img"
				/>
				<div class="card__content--article">
					<h6 class="writer__name">{{ writerName }}</h6>
					<h4 class="title">
						<a :href="link">{{ header }}</a>
					</h4>
					<p class="lead">
						{{ lead }}
					</p>
				</div>
			</div>
</template>

<script>
export default {
props: {
  image: {
    type: String,
    require: true
  },
  alt: {
    type: String,
    require: true
  },
  writerName: {
    type: String,
    require: true
  },
  header: {
    type: String,
    require: true
  },
  link: {
    type: String,
    require: true
  },
  lead: {
    type: String,
    require: true
  },
}
}
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";
.card--img {
	width: 100%;
	height: 175px;
}
.card__content--article {
	background-color: #fff;
	padding: 1.5em 1.2em;
	font-weight: var(--fw-sm);
}
.writer__name {
	color: var(--GrayishBlue);
	font-weight: var(--fw-sm);
	font-size: 0.7rem;
}
.title {
	color: var(--DarkBlue);
	font-weight: var(--fw-md);
	margin: 0.7em 0;
	font-size: 1.1rem;
	@media (min-width: 710px) {
		font-size: 1rem;
	}
}
.title a {
	color: var(--DarkBlue);
	transition: 0.3s all linear;
}
.title a:hover {
	color: var(--BrightCyan);
}
.lead {
	color: var(--GrayishBlue);
	font-size: 0.7rem;
	line-height: 1.5;
}
</style>