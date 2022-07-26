<template>
  <div>
    <img
      :src="require(`../assets/${image}`)"
      :alt="alt"
      class="card--icon"
    />
    <div class="card__content">
      <h4 class="card__header">{{ header }}</h4>
      <p class="description description--about-card">
        {{ description }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    },
    header: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
  }
}
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";

.card--about {
	text-align: center;
	@media (min-width: 680px) {
		text-align: left;
	}
}
.card--icon {
	width: 3em;
}
.card__header {
	margin: 1em 0;
	font-weight: var(--fw-md);
}
.description--about-card {
	font-size: 0.95rem;
	max-width: 100%;
	margin-inline: auto;
	@media (min-width: 680px) {
		max-width: 250.5px;
		margin-inline: 0;
	}
}
</style>