<script lang="ts">
    import {auth, user} from "$lib/firebase";
    import { GoogleAuthProvider, signInWithPopup, signOut } from "firebase/auth";

    async function signInWithGoogle() {
        const provider = new GoogleAuthProvider();
        const user = await signInWithPopup(auth, provider);
        console.log(user)
    }


</script>

{#if $user}
    <div class="flex flex-col">
        <h2>Welcome, {$user.displayName}</h2>
        <p class="text-center text-secondary-500">You are logged in</p>
        <button type="button" class="mt-5 btn variant-filled-primary" on:click={() => signOut(auth)}>Sign out</button>
    </div>

{:else}
    <button type="button" class="btn variant-filled-primary" on:click={signInWithGoogle}>Sign in with Google</button>
{/if}