<script>
	import { onMount } from 'svelte';
	onMount(() => {
		// redirect to https://top.gg
		window.location.href = 'https://top.gg/bot';
	});
	let class1 = 'hidden';
	let class2 = 'visible';
	setTimeout(() => {
		class1 = 'visible';
		class2 = 'hidden';
	}, 200);
</script>

<p class={class1}>
	if you are not redirected automatically, follow this <a
		href="https://top.gg"
		class="text-cyan-500">link</a
	>
</p>
<p class={class2}>
	Redirecting to <a href="https://top.gg"
		>https://top.gg</a
	>
</p>
