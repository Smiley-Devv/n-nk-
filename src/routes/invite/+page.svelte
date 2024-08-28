<script>
	import { onMount } from 'svelte';
	onMount(() => {
		// redirect to https://discord.com/oauth2/authorize?client_id=1267489812521160805
		window.location.href = 'https://discord.com/oauth2/authorize?client_id=1267489812521160805';
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
		href="https://discord.com/oauth2/authorize?client_id=1267489812521160805"
		class="text-cyan-500">link</a
	>
</p>
<p class={class2}>
	Redirecting to <a href="https://discord.com/oauth2/authorize?client_id=1090120136167538748"
		>https://discord.com/oauth2/authorize?client_id=1090120136167538748</a
	>
</p>
