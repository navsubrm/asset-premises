<script>
	import { gsap } from '@gsap/simply/dist/gsap.js';
	import DrawSVGPlugin from '@gsap/simply/dist/DrawSVGPlugin';
	import { onMount } from 'svelte';
	//Do stuff.

	onMount(() => {
		handleIntroAnimation();
	});

	async function handleIntroAnimation() {
		gsap.registerPlugin(DrawSVGPlugin);
		const tl = gsap.timeline();
		tl.from(
			['#branch-1', '#branch-2', '#branch-3'],
			{ duration: 0.25, delay: 0.5, opacity: 0, drawSVG: '90% 100%' },
			'<'
		);
		tl.to('#fill-grad-green stop', 1.25, { attr: { offset: '0%' }, ease: 'none' }, '<');
		tl.to('#fill-grad-gold stop', 1.25, { attr: { offset: '0%' }, ease: 'none' }, '>');
	}
</script>

<header>
	<div class="header-title">
		<div class="upper-line">
			<h3>Asset Premises</h3>
			<p>Growth Through Transparency</p>
		</div>
		<svg
			fill="#000000"
			version="1.1"
			id="Capa_1"
			xmlns="http://www.w3.org/2000/svg"
			xmlns:xlink="http://www.w3.org/1999/xlink"
			width="800px"
			height="800px"
			viewBox="0 0 487.243 487.243"
			xml:space="preserve"
		>
			<g>
				<defs>
					<linearGradient id="fill-grad-gold" x1="0%" y1="0%" x2="0%" y2="100%">
						<stop offset="100%" stop-color="transparent" />
						<stop offset="100%" stop-color="color-mix(in lab, var(--gold), transparent 15%)" />
					</linearGradient>
				</defs>

				<defs>
					<linearGradient id="fill-grad-green" x1="0%" y1="0%" x2="0%" y2="100%">
						<stop offset="100%" stop-color="transparent" />
						<stop offset="100%" stop-color="color-mix(in lab, var(--green), transparent 15%)" />
					</linearGradient>
				</defs>

				<path
					id="branch-1"
					fill="url(#fill-grad-green)"
					d="M196.832,302.479c-0.225-22.92-15.482-66.853-36.727-88.086c-21.245-21.234-65.598-32.276-88.061-36.708
                   c-3.154-0.623-6.408,0.376-8.661,2.644c-2.286,2.272-3.28,5.521-2.64,8.667c4.414,22.484,15.451,66.852,36.695,88.077
                   c15.611,15.62,43.707,25.693,66.436,31.708v161.981c0,9.103,7.366,16.481,16.477,16.481c9.109,0,16.48-7.38,16.48-16.481
                   C196.832,470.763,196.894,309.612,196.832,302.479z"
				/>
				<path
					id="branch-2"
					fill="url(#fill-grad-gold)"
					d="M262.751,124.978c-0.13-22.921-15.481-66.852-36.727-88.088C204.78,15.655,160.426,4.614,137.96,0.182
                   c-3.154-0.623-6.404,0.376-8.657,2.644c-2.286,2.272-3.284,5.521-2.64,8.666c4.409,22.486,15.451,66.853,36.695,88.079
                   c15.607,15.621,43.707,25.694,66.43,31.708v339.483c0,9.103,7.372,16.481,16.482,16.481c9.108,0,16.479-7.38,16.479-16.481
                   C262.751,470.763,262.813,136.902,262.751,124.978z"
				/>
				<path
					id="branch-3"
					fill="url(#fill-grad-green)"
					d="M426.514,139.555c0.614-3.146-0.386-6.395-2.64-8.666c-2.285-2.268-5.533-3.266-8.657-2.644
                   c-22.499,4.432-66.854,15.473-88.097,36.708c-21.24,21.235-36.658,63.929-36.688,88.086
                   c-0.031,15.634-0.031,217.723-0.031,217.723c0,9.103,7.371,16.481,16.478,16.481c9.108,0,16.479-7.38,16.479-16.481V259.34
                   c22.754-6.013,50.854-16.086,66.468-31.707C411.063,206.406,422.104,162.04,426.514,139.555z"
				/>
			</g>
		</svg>
	</div>

	<nav>
		<ul>
			<li>Home</li>
			<li>About</li>
			<li>Customer Portal</li>
			<li>Management Portal</li>
		</ul>
	</nav>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1em;
		font-size: 1.2em;
		border-bottom: solid 1px var(--blue);
		background: linear-gradient(
			to top,
			var(--blue) 1%,
			color-mix(in lab, var(--blue), var(--white) 40%) 3% 5%,
			var(--white) 15% 100%
		);
	}

	.header-title {
		display: flex;
		align-items: flex-end;
		color: var(--blue);
	}

	.header-title h3 {
		font-size: 1.35em;
	}

	.header-title p {
		font-size: 0.8em;
	}

	nav ul {
		display: flex;
		gap: 1em;
		list-style: none;
	}

	nav ul li {
		text-decoration: none;
	}

	header svg {
		height: 50px;
		width: 50px;
	}

	#branch-1,
	#branch-3 {
		stroke: var(--gold);
		stroke-width: 3;
	}
</style>
