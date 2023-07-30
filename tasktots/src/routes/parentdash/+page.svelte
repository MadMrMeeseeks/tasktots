<script lang="ts">
    import { userData, docStore, auth, db } from "$lib/firebase";
    import { updateDoc, setDoc, doc } from "firebase/firestore";
    import type { Chore } from "$lib/firebase"
    import { onMount } from 'svelte';
    import Icon from "@iconify/svelte"
    let choreList: Chore[] = [];
    let choreName = '';
    let choreDesc = '';
    let choreValue = '';
    let choreStatus = false;

    // Fetch the chore list when the component mounts
    onMount(async () => {
        userData.subscribe((data) => {
            if (data?.choreList) {
                choreList = data.choreList;
            }
        });
    });

    const addChore = () => {
        const chore: Chore = {
            choreName: choreName,
            choreDesc: choreDesc,
            choreValue: parseInt(choreValue),
            choreStatus: choreStatus,
        };
        choreList = [...choreList, chore];
        // Update user data in Firebase
        updateUserData(choreList);
    };

    // We can use docStore for this because it already has reference to the user document
    const updateUserData = async (choreList: Chore[]) => {
        const userRef = doc(db, `users/${auth.currentUser?.uid}`);
        // Assuming choreList is an array in userData
        await updateDoc(userRef, { choreList: choreList });
    };


    function handleEditClick() {
        // Logic for handling the click event goes here.
    }

    function handleDeleteClick() {
        // Logic for deleting a chore
    }
</script>






<div class="mt-20 mx-40">
    <!-- Native Table Element -->
    <table class="table">
        <thead>
        <tr>
            <th>Chore</th>
            <th>Description</th>
            <th class="w-0.5 text-center">Points</th>
            {#if choreList.length > 0}
                <th class="w-0.5 text-center">Is Complete?</th>
            {:else}
                <th class="w-0.5 text-center"></th>
            {/if}
            <th class="w-0.5"></th>
            <th class="w-0.5"></th>
        </tr>
        </thead>
        <tbody>
        {#each choreList as chore (chore.choreName)}
            <tr>
                <td>{chore.choreName}</td>
                <td>{chore.choreDesc}</td>
                <td class="text-center">{chore.choreValue}</td>
                <td class="flex justify-center items-center"><input class="checkbox justify-center" type="checkbox" bind:checked={chore.choreStatus} /></td>
                <td>
                    <div class="cursor-pointer" on:click={handleEditClick}>
                        <Icon icon="akar-icons:edit" style="font-size: 18px;" />
                    </div>
                </td>
                <td>
                    <div class="cursor-pointer" on:click={handleDeleteClick}>
                        <Icon icon="jam:trash" style="font-size: 18px;" />
                    </div>
                </td>
            </tr>
        {/each}
        <tr>
            <td><input bind:value={choreName} class="input" type="text" placeholder="Chore Name" /></td>
            <td><input bind:value={choreDesc} class="input" type="text" placeholder="Chore Description" /></td>
            <td><input bind:value={choreValue} class="input no-spinner text-center" type="number" placeholder="0" /></td>
            <td><button type="button" class="btn variant-filled-primary" on:click={addChore}>Add/Update</button></td>
            <td></td>
            <td></td>
        </tr>
        </tbody>
    </table>
</div>
