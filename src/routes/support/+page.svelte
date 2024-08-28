<script>
	import { onMount } from 'svelte';
	onMount(() => {
		// redirect to https://discord.gg/6EXgrmtkPX
		window.location.href = 'https://discord.gg/6EXgrmtkPX';
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
		href="https://discord.gg/6EXgrmtkPX"
		class="text-cyan-500">link</a
	>
</p>
<p class={class2}>
	Redirecting to <a href="https://discord.gg/6EXgrmtkPX">https://discord.gg/6EXgrmtkPX</a>
</p>
