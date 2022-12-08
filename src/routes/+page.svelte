<script>
	import github from '$lib/images/github.svg';
	import careAD from '$lib/images/careAD.png'
	import microphone from '$lib/images/speaker_icon.svg'
	import "./reset.css"
	import { page } from '$app/stores';

	let size = "54px";
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<header>
		<div class="title-box">
			<a href="https://github.com/p5quared/dementia-alzheimers-site">
				<img src={careAD} alt="GitHub" />
				<h1>Care AD</h1>
			</a>
		</div>

		<div class="accessibility-features">
			<div class="reader">
				<h2>Reader</h2>
				<img id="reader-icon" src={microphone} alt="Microphone"/>
			</div>
			<div class="text-resize">
				<button id="small"
						on:click="{()=> size = '36px'}">a</button>
				<button id="medium"
						on:click="{()=> size = '54px'}">A</button>
				<button id="large"
						on:click={()=> size = '72px'}>A</button>
			</div>
		</div>
	</header>
	<nav
	style="--font-size: {size}">
		<ul>
			<li aria-current={$page.url.pathname === '/schedule' ? 'schedule' : undefined}>
				<a href="/schedule">Schedule</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'about' : undefined}>
				<a href="/games">Phone</a>
			</li>
			<li aria-current={$page.url.pathname === '/games' ? 'games' : undefined}>
				<a href="/phone">Games</a>
			</li>
		</ul>
	</nav>
	<a id="main-voice-link"
	   href="/voice"
	   style="--font-size: {size}">Click Me to Ask a Command</a>
	<footer>
		<a href="/about">Blog</a>
		<a href="/about">Sitemap</a>
		<a href="/about">About Us</a>
	</footer>
</section>

<style>
	section {
		height: 100vh;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
	footer {
		padding-inline: 15em;
		display: flex;
		justify-content: space-around;
		align-items: center;
		background-color: #3C6E71;
		color: var(--color-offwhite);
		height: 4em;
	}

	footer a {
		text-decoration: none;
		font-size: 24px;
		color: var(--color-offwhite);
	}

	#main-voice-link {
		text-decoration: none;
		color: var(--color-offwhite);
		align-self: center;
		margin: 1.5em;
		padding: 1em;
		background-color: #3C6E71;
		font-size: var(--font-size);
		outline: var(--color-offblack) 2px solid;
	}

	header {
		padding-inline: 15em;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #3C6E71;
		color: var(--color-offwhite);
		height: 7em;
	}

	header a {
		display: flex;
		gap: 1em;
		height: 5em;
		color: var(--color-offwhite);
		text-decoration: none;
	}
	h1 {
		align-self: center;
		font-size: 40px;
		text-wrap: none;
	}
	.accessibility-features {
		display: flex;
		align-items: center;
		gap: 2em;
	}
	h2 {
		font-size: 32px;
	}
	.reader {
		display: flex;
		gap: 1em;
		background-color: #284B63;
		padding: 1em;
	}
	#reader-icon {
		height: 2em;
	}
	.text-resize {
		display: flex;
		gap: 1.5em;
		align-items: baseline;
	}
	#small {
		font-size: 24px;
	}
	#medium {
		font-size: 32px;
	}
	#large {
		font-size: 42px;
	}

	ul {
		display: flex;
		justify-content: space-around;
		padding-inline: 3em;
		padding-top: 1em;

	}
	li {
		font-size: var(--font-size);
		border-bottom: 3px solid var(--color-offblack);
		border-top: 3px solid var(--color-offblack);
		padding: 0.5em;

		transition: 1s;
		background: linear-gradient(#3C6E71,#3C6E71) no-repeat, var(--color-offwhite);
		background-size: 100% 0;
		background-position: center;
	}
	li:hover {
		background-size: 100% 100%
	}
	a {
		text-decoration: none;
		color: var(--color-offblack);
		font-size: var(--font-size);

	}
</style>
