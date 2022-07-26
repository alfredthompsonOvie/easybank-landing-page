<template>
	<footer class="section section--footer">
		<div class="footer__content">
			<div class="branding--footer">
				<a href="#">
					<img src="@/assets/logo.svg" alt="" class="logo--footer" />
				</a>
				<ul class="social__media__list">
					<li>
						<a href="#" class="social__link">
							<img src="@/assets/icon-facebook.svg" alt="facebook logo" />
						</a>
					</li>
					<li>
						<a href="#" class="social__link">
							<img src="@/assets/icon-youtube.svg" alt="youtube logo" />
						</a>
					</li>
					<li>
						<a href="#" class="social__link">
							<img src="@/assets/icon-twitter.svg" alt="twitter logo" />
						</a>
					</li>
					<li>
						<a href="#" class="social__link">
							<img src="@/assets/icon-pinterest.svg" alt="pinterest logo" />
						</a>
					</li>
					<li>
						<a href="#" class="social__link">
							<img src="@/assets/icon-instagram.svg" alt="instagram logo" />
						</a>
					</li>
				</ul>
			</div>
			<div class="footer__links">
				<ul class="nav__list__sec">
					<li><a href="#" class="nav__link--footer">About Us</a></li>
					<li><a href="#" class="nav__link--footer">Contact</a></li>
					<li><a href="#" class="nav__link--footer">Blog</a></li>
				</ul>
				<ul class="nav__list__sec">
					<li><a href="#" class="nav__link--footer">Careers</a></li>
					<li><a href="#" class="nav__link--footer">Support</a></li>
					<li><a href="#" class="nav__link--footer">Privacy Policy</a></li>
				</ul>
			</div>
			<div class="branding--footer copyright--container">
				<a href="#" class="cta cta--default cta--footer">Request Invite</a>
				<p class="copyright">©Easybank. All Rights Reserved</p>
			</div>
		</div>
		<div class="attribution">
			Challenge by
			<a href="https://www.frontendmentor.io?ref=challenge" target="_blank"
				>Frontend Mentor</a
			>. Coded by
			<a href="https://www.linkedin.com/in/alfredthompsonovie/" target="_blank"
				>Alfred Thompson Ovie</a
			>.
		</div>
	</footer>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import "../scss/main.scss";
.section--footer {
	background-color: var(--DarkBlue);
}
.footer__content {
	grid-row: 1;
	grid-column: 2;
	text-align: center;
	padding-bottom: 2em;
}
.branding--footer {
	display: flex;
	align-items: center;
	justify-content: space-between;
	flex-direction: column;
	gap: 2em;
}
.logo--footer {
	filter: contrast(2) invert(1) hue-rotate(220deg) brightness(2);
}
.social__media__list {
	display: flex;
	align-items: center;
	justify-content: center;
	gap: 1.2em;
}
.social__link img {
	transition: all 0.3s linear;
}
.social__link:hover img {
	filter: sepia(1) saturate(9) hue-rotate(100deg) brightness(0.8) contrast(2);
}
.footer__links {
	margin: 2em 0;
}
.nav__list__sec {
	display: flex;
	align-items: center;
	justify-content: space-between;
	flex-direction: column;
	gap: 1.2em;
}
.nav__list__sec:nth-child(2) {
	margin-top: 1.2em;
}
.nav__link--footer {
	color: var(--VeryLightGray);
	font-size: 0.9rem;
	font-weight: var(--fw-md);
	transition: all 0.3s linear;
}
.nav__link--footer:hover {
	color: var(--LimeGreen);
}
.section--footer .cta--footer:hover {
    --LimeGreenHover: hsl(136, 89%, 75%);
	--BrightCyanHover: hsl(192, 89%, 76%);
	
  --linearGradientHover: linear-gradient(90deg, var(--LimeGreenHover),      
  var(--BrightCyanHover));
	opacity: 1;
	background-image: var(--linearGradientHover);
}
.copyright {
	color: var(--LightGrayishBlue);
	font-weight: var(--fw-sm);
	font-size: 0.8rem;
}

@media (min-width: 992px) {
	.section--footer {
		padding-bottom: 1em;
	}
	.footer__content {
		grid-row: 1;
		grid-column: 2;
		text-align: left;
		padding-bottom: 2em;
		display: flex;
		gap: 5em;
	}
	.footer__links {
		margin: 0;
		display: flex;
		gap: 5em;
	}
	.branding--footer {
		align-items: flex-start;
	}
	.nav__list__sec {
		align-items: flex-start;
	}
	.nav__list__sec:nth-child(2) {
		margin-top: 0em;
	}
	.copyright--container {
		margin-left: auto;
		align-items: flex-end;
	}
}
</style>
