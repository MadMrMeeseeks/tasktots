<script lang="ts">
    import { user } from "$lib/firebase";
</script>

{#if $user}
    <slot />
{:else}
    <p class="text-error-500">
        You must be signed in to view this page.
        <a class="btn btn-primary=500" href="/login">Sign in</a>
    </p>
{/if}