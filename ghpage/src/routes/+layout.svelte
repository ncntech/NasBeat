<script>
        import '../app.css';
        import { base } from '$app/paths';

        let { children } = $props();
</script>

<svelte:head>
        <link rel="icon" href="{base}/nasbeat-logo-red.png" type="image/png" />
</svelte:head>

<main>
        {@render children?.()}
</main>
