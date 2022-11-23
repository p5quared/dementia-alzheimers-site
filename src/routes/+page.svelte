<script>
	import Header from "./Header.svelte";
	import "./styles.css"
	import Navigation from "./Navigation.svelte";
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Header />
	<Navigation />
	<a id="main-voice-link" href="/voice">Click Me to Ask a Command</a>
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
		font-size: 52px;
		align-self: center;
		margin: 1.5em;
		padding: 1em;
		background-color: #3C6E71;
		outline: var(--color-offblack) 2px solid;
	}
</style>
