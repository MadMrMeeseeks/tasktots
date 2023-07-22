<script lang="ts">
    import { onMount } from 'svelte';
    import { tableMapperValues } from '@skeletonlabs/skeleton';
    import { Table, TabGroup, Tab, CodeBlock, type TableSource } from '@skeletonlabs/skeleton';

    const sourceData = [
        { position: 1, name: 'Clean', desc: "Make sure to clean", points: '10', isComplete: '<label class="flex items-center justify-center space-x-2"><input class="checkbox" type="checkbox" /></label>', edit: '<button class="btn-edit"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"><path d="M7 7H6a2 2 0 0 0-2 2v9a2 2 0 0 0 2 2h9a2 2 0 0 0 2-2v-1"/><path d="M20.385 6.585a2.1 2.1 0 0 0-2.97-2.97L9 12v3h3l8.385-8.415zM16 5l3 3"/></g></svg></button>' },
    ];

    const tableSimple: TableSource = {
        // A list of heading labels.
        head: ['Chore', 'Description', 'Points', 'Complete?', ''],
        // The data visibly shown in your table body UI.
        body: tableMapperValues(sourceData, ['name', 'desc', 'points', 'isComplete', 'edit']),
        // Optional: The data returned when interactive is enabled and a row is clicked.
        meta: tableMapperValues(sourceData, ['position', 'name', 'desc', 'points', 'isComplete', 'edit']),
        // Optional: A list of footer labels.
        foot: ['<input class="input" title="Input (text)" type="text" placeholder="input text" />', '<input class="input" title="Input (text)" type="text" placeholder="input text" />', '<input class="input" title="Input (text)" type="text" placeholder="input text" />', '<button type="button" class="btn btn-sm variant-filled">update</button>']
    };

    function handleEditClick(event) {
        // Access the event target
        const btn = event.target;

        // Do something when the button is clicked
        console.log('Button clicked:', btn);
    }

    onMount(() => {
        const buttons = document.querySelectorAll('.btn-edit');
        buttons.forEach(btn => {
            btn.addEventListener('click', handleEditClick);
        });
    });
</script>

<div class="mt-20 mx-20">
    <Table source={tableSimple} regionHeadCell="text-center" regionCell="text-center" regionFootCell="text-center" />
</div>



