<script>
	import { page } from '$app/stores';
</script>

<div class="container">
	{#if $page.error}
		{#if $page.error.status === 404}
			<h1>Oops! This page is as lost as a penguin in the desert.</h1>
			<p>
				Looks like you've ventured into uncharted territory. But don't worry, you can always head
				back home.
			</p>
		{:else}
			<h1>Oops! Something went wrong.</h1>
			<p>
				Looks like there's a glitch in the matrix. But don't worry, you can always head back home.
			</p>
		{/if}
	{:else}
		<h1>Loading...</h1>
	{/if}
	<a href="/" class="text-cyan-500">Go back home.</a>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
		text-align: center;
	}
</style>
