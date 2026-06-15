<script>
	import '../app.css';
	
	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href="/nasbeat-logo-red.png" type="image/png" />
</svelte:head>

<main>
	{@render children?.()}
</main>
