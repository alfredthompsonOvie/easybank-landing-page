<template>
	<header>
		<nav class="nav__bar">
			<img
				src="@/assets/logo.svg"
				alt="an image of Easybank's logo"
				class="site__logo"
			/>
			<ul v-show="!mobile" class="nav__list">
				<li class="nav__item">
					<router-link :to="{ name: 'home' }" class="nav__link">
						<span>Home</span>
						<span class="link--bg"></span>
					</router-link>
				</li>
				<li class="nav__item">
					<router-link :to="{ name: '' }" class="nav__link"
						>About
						<span class="link--bg"></span>
					</router-link>
				</li>
				<li class="nav__item">
					<router-link :to="{ name: '' }" class="nav__link"
						>Contact
						<span class="link--bg"></span>
					</router-link>
				</li>
				<li class="nav__item">
					<router-link :to="{ name: '' }" class="nav__link"
						>Blog
						<span class="link--bg"></span>
					</router-link>
				</li>
				<li class="nav__item">
					<router-link :to="{ name: '' }" class="nav__link"
						>Careers
						<span class="link--bg"></span>
					</router-link>
				</li>
			</ul>
			<button-component v-show="!mobile" />
			<div class="hamburger" v-show="mobile">
				<button
					@click="openMenu"
					v-show="openMobileMenu"
					class="btn--menu btn--open__menu"
				>
					<img
						src="@/assets/icon-hamburger.svg"
						alt="an icon to display the mobile menu"
						class="open__menu menu"
					/>
				</button>
				<button
					@click="closeMenu"
					v-show="closeMobileMenu"
					class="btn--menu btn--close__menu is--hidden"
				>
					<img
						src="@/assets/icon-close.svg"
						alt="an icon to display the mobile menu"
						class="close__menu menu"
					/>
				</button>
			</div>
			<transition name="mobile-nav">
				<ul v-show="mobileNav" class="dropdown nav__list--mobile">
					<li class="nav__item">
						<router-link :to="{ name: 'home' }" class="nav__link--mobile"
							>Home</router-link
						>
					</li>
					<li class="nav__item">
						<router-link :to="{ name: '' }" class="nav__link--mobile"
							>About</router-link
						>
					</li>
					<li class="nav__item">
						<router-link :to="{ name: '' }" class="nav__link--mobile"
							>Contact</router-link
						>
					</li>
					<li class="nav__item">
						<router-link :to="{ name: '' }" class="nav__link--mobile"
							>Blog</router-link
						>
					</li>
					<li class="nav__item">
						<router-link :to="{ name: '' }" class="nav__link--mobile"
							>Careers</router-link
						>
					</li>
				</ul>
			</transition>
				<div class="overlay" v-show="closeMobileMenu"></div>
		</nav>
	</header>
</template>

<script>
import ButtonComponent from "./ButtonComponent.vue";
export default {
	name: "navigationBar",
	components: {
		ButtonComponent,
	},
	data() {
		return {
			mobile: null,
			mobileNav: null,
			windowWidth: null,
			openMobileMenu: true,
			closeMobileMenu: false,
		};
	},
	created() {
		window.addEventListener("resize", this.checkScreen);
		this.checkScreen();
	},
	methods: {
		openMenu() {
			this.openMobileMenu = false;
			this.closeMobileMenu = true;
			this.mobileNav = true;
		},
		closeMenu() {
			this.openMobileMenu = true;
			this.closeMobileMenu = false;
			this.mobileNav = false;
		},
		checkScreen() {
			this.windowWidth = window.innerWidth;
			if (this.windowWidth < 992) {
				this.mobile = true;
				return;
			}
			this.mobile = false;
			this.mobileNav = false;
			return;
		},
	},
};
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";
header {
	display: grid;
	grid-template-columns: 0.1fr 1.8fr 0.1fr;
	grid-template-rows: auto;
	background-color: #fff;
	position: relative;
	z-index: 10;
	@media (min-width: 992px) {
		padding: 0;
	}
	@media (min-width: 1300px) {
		grid-template-columns: 0.2fr 1.6fr 0.2fr;
		grid-template-columns: 0.15fr 1.7fr 0.15fr;
	}
	@media (min-width: 1400px) {
		grid-template-columns: 0.2fr 1.6fr 0.2fr;
	}
}
.nav__bar {
	grid-column: 2;
	grid-row: 1;
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 1.2em 0;
	position: relative;
	z-index: 8;
	@media (min-width: 992px) {
		padding: 0;
	}
}
.nav__list--mobile {
	width: 100%;
	position: absolute;
	top: 5em;
	left: 0;
	padding: 1em;
	background-color: var(--VeryLightGray);
	border-radius: 8px;
	text-align: center;
	z-index: 5;
}
.nav__link--mobile {
	display: block;
	padding: 0.6em;
	color: var(--DarkBlue);
	font-weight: var(--fw-md);
}
.hamburger {
	position: relative;
	width: 28px;
	height: 26px;
	z-index: 99;
}
.btn--menu {
	position: absolute;
	width: 100%;
	height: 100%;
	background-color: transparent;
	border: none;
	cursor: pointer;
}
.overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.3);
	z-index: 1;
}
.nav__list {
	display: inline-flex;
	align-items: center;
	gap: 1em;
	padding: 0;
}
.nav__item {
	height: 100%;
}
.nav__link {
	font-size: 1rem;
	color: var(--GrayishBlue);
	height: 100%;
	padding: 2em 0;
	position: relative;
	transition: all 0.6s linear;
	overflow: hidden;
	display: block;
}
.nav__link:hover {
	color: var(--DarkBlue);
}
.link--bg {
	width: 100%;
	height: 4px;
	background-image: var(--linearGradient);
	position: absolute;
	bottom: 0;
	left: 0;
	transform: translateX(-100%);
	transition: all 0.3s linear;
}
.nav__link:hover .link--bg {
	transform: translateX(0%);
}
</style>
