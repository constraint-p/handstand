<script>
	import PouchDb from '../components/PouchDb.svelte';

	let handstandInProgress = false;

	function handstandStarted() {
		handstandInProgress = true;
	}
	function handstandStopped() {
		handstandInProgress = false;
	}

</script>


<svelte:head>
	<title>Sapper project template</title>
</svelte:head>

<h2>No handstand yet today</h2>

{#if handstandInProgress}
	<h2>Handstand in progress..</h2>
{:else}
	<h2>No handstand in progress</h2>
{/if}

<button on:mousedown="{handstandStarted}" on:mouseup="{handstandStopped}" on:mouseleave="{handstandStopped}">Perform Handstand</button>

<PouchDb>Pouchy</PouchDb>

<style>
	h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>
