<script lang="ts">
    import { tableMapperValues } from '@skeletonlabs/skeleton';
    import { Table, TabGroup, Tab, CodeBlock, type TableSource } from '@skeletonlabs/skeleton';

    const sourceData = [
        { position: 1, name: 'Clean Basement', desc: "Tidy the boys side of the basement", points: '10', isComplete: 'no' },
    ];

    const tableSimple: TableSource = {
        // A list of heading labels.
        head: ['Chore', 'Description', 'Points', 'Complete?'],
        // The data visibly shown in your table body UI.
        body: tableMapperValues(sourceData, ['name', 'desc', 'points', 'isComplete']),
        // Optional: The data returned when interactive is enabled and a row is clicked.
        meta: tableMapperValues(sourceData, ['position', 'name', 'desc', 'points', 'isComplete']),
        // Optional: A list of footer labels.
        foot: ['Total', '', '<code class="code">5</code>', '']
    };



</script>

<div class="mt-20 mx-20">
    <Table source={tableSimple} />
</div>
