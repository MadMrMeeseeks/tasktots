<script lang="ts">
    import { tableMapperValues } from '@skeletonlabs/skeleton';
    import { Table, TabGroup, Tab, CodeBlock, type TableSource } from '@skeletonlabs/skeleton';
    import Icon from '@iconify/svelte';


    const sourceData = [
        { position: 1, name: 'Clean', desc: "Make sure to clean", points: '10', isComplete: '<label class="flex items-center justify-center space-x-2"><input class="checkbox" type="checkbox" /></label>', edit: '<iconify-icon icon="tabler:edit"></iconify-icon>' },
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
</script>

<div class="mt-20 mx-20">
    <Table source={tableSimple} regionHeadCell="text-center" regionCell="text-center" regionFootCell="text-center" />
</div>
