<script lang="ts">
    import { userData } from "$lib/firebase";
</script>

<svelte:head>
    <title>Test Page</title>
</svelte:head>

{#if $userData}
    <h1>{$userData.bio}</h1>
{:else}
    <h1>Loading bio...</h1>
{/if}


