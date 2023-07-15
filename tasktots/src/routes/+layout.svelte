<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
    import '@skeletonlabs/skeleton/themes/theme-modern.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
    import { AppShell } from '@skeletonlabs/skeleton';
    import { AppBar } from '@skeletonlabs/skeleton';
    import Icon from "@iconify/svelte"
    import { Drawer, drawerStore } from '@skeletonlabs/skeleton';


</script>

<Drawer let:data={drawerData}>
    <!-- use the drawerData here -->
</Drawer>

<AppShell slotPageContent="bg-surface-500">
    <svelte:fragment slot="header">
        <!-- App Bar -->
        <AppBar shadow="custom-shadow" background="bg-surface-800">
            <svelte:fragment slot="lead">
                <Icon icon="mingcute:check-2-line" style="font-size: 30px;"></Icon>
                <strong class="ml-2 text-xl uppercase">Task Tots</strong>
            </svelte:fragment>
            <svelte:fragment slot="trail">
                <span>About</span>
                <span>Blog</span>
                <button type="button" class="btn variant-filled-primary">Get Started!</button>
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



