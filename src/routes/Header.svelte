<script>
	import github from '$lib/images/github.svg';
	import microphone from '$lib/images/speaker_icon.svg'

</script>

<header>
	<div class="title-box">
		<a href="https://github.com/p5quared/dementia-alzheimers-site">
			<img src={github} alt="GitHub" />
			<h1> Site Name</h1>
		</a>
	</div>
	<div class="accessibility-features">
		<div class="reader">
			<h2>Reader</h2>
			<img id="reader-icon" src={microphone} alt="Microphone"/>
		</div>
		<div class="text-resize">a a A</div>
	</div>


</header>

<style>
	header {
		padding-inline: 15em;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background-color: #3C6E71;
		color: var(--color-offwhite);
		height: 7em;
	}
	a {
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

</style>
