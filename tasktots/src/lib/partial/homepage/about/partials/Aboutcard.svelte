<script>
    import {Accordion, AccordionItem} from "@skeletonlabs/skeleton";
    import Icon from "@iconify/svelte"
</script>


<div class="card">

    <Accordion autocollapse={true}>
        <AccordionItem open>
            <svelte:fragment slot="lead">
                <Icon icon="fluent-emoji-high-contrast:person" style="font-size: 30px;"></Icon>
            </svelte:fragment>
            <svelte:fragment slot="summary">Who are we?</svelte:fragment>
            <svelte:fragment slot="content">This will be some super cool block of text explaining who we are. Make it relatable and catchy and something that will encourage other parents to engage with the site and the tools that we are creating </svelte:fragment>
        </AccordionItem>
        <AccordionItem>
            <svelte:fragment slot="lead">
                <Icon icon="uil:create-dashboard" style="font-size: 30px;"></Icon>
            </svelte:fragment>
            <svelte:fragment slot="summary">Why Did We Create Task Tots?</svelte:fragment>
            <svelte:fragment slot="content">This will be content describing what lead us to want to create task tots. Should include what we hope users will stand to gain from using the tools. </svelte:fragment>
        </AccordionItem>
        <AccordionItem>
            <svelte:fragment slot="lead">
                <Icon icon="mingcute:question-line" style="font-size: 30px;"></Icon>
            </svelte:fragment>
            <svelte:fragment slot="summary">Who is it For?</svelte:fragment>
            <svelte:fragment slot="content">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia </svelte:fragment>
        </AccordionItem>
        <AccordionItem>
            <svelte:fragment slot="lead">
                <Icon icon="fluent-mdl2:renewal-future" style="font-size: 30px;"></Icon>
            </svelte:fragment>
            <svelte:fragment slot="summary">Future Plans for Task Tots</svelte:fragment>
            <svelte:fragment slot="content">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat</svelte:fragment>
        </AccordionItem>
        <!-- ... -->
    </Accordion>

</div>

