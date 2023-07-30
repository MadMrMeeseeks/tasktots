<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
    import '@skeletonlabs/skeleton/themes/theme-modern.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
    import { goto } from '$app/navigation';
    import { AppShell } from '@skeletonlabs/skeleton';
    import { AppBar } from '@skeletonlabs/skeleton';
    import Icon from "@iconify/svelte"

    import {auth, user} from "$lib/firebase";
    import { GoogleAuthProvider, signInWithPopup, signOut } from "firebase/auth";


    async function handleSignOut() {
        try {
            await signOut(auth);
            goto('/');
        } catch (error) {
            console.error("Error signing out: ", error);
        }
    }


</script>


<AppShell slotPageContent="bg-surface-500">
    <svelte:fragment slot="header">
        <!-- App Bar -->
        <AppBar shadow="custom-shadow" background="bg-surface-800">
            <svelte:fragment slot="lead">
                <Icon icon="mingcute:check-2-line" style="font-size: 30px;"></Icon>
                <a href="/"><strong class="ml-2 text-xl uppercase">Task Tots</strong></a>
            </svelte:fragment>
            <svelte:fragment slot="trail">
                <span>Blog</span>
                <a href="/parentdash">Parents</a>
                {#if $user}
                    <button type="button" class="btn variant-filled-primary" on:click={handleSignOut}>Sign out</button>
                    {:else}
                    <a href="/login"><button type="button" class="btn variant-filled-primary">Get Started!</button></a>
                    {/if}
            </svelte:fragment>
        </AppBar>
    </svelte:fragment>
    <svelte:fragment slot="pageFooter">
        <AppBar>
            <svelte:fragment slot="lead">(icon)</svelte:fragment>
            (title)
            <svelte:fragment slot="trail">(actions)</svelte:fragment>
        </AppBar>
    </svelte:fragment>

    <slot />

</AppShell>



