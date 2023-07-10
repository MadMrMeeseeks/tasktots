<script>
    import {ListBox, ListBoxItem} from "@skeletonlabs/skeleton";
    import Aboutcard from '$lib/partial/homepage/about/partials/Aboutcard.svelte'
    import Blogcard from '$lib/partial/homepage/about/partials/Blogcard.svelte'
    let valueSingle = 'about';
</script>


<div class="flex justify-center space-x-20 mt-32 mb-32">
    <div class="flex-col justify-center space-y-2 items-center max-w-md">
        <div>
            <h1 class="h1">
                <span class="text-white">Designed to Make Achieving Goals Fun!</span>
            </h1>
            <h1 class="h4">
                <span class="text-white">Task Tots helps you set goals for your children and to discover new ways to build the skills they need to succeed</span>
            </h1>
        </div>
        <div>
            <ListBox padding="py-8" rounded="rounded-3xl">
                <ListBoxItem bind:group={valueSingle} name="medium" value="about" class="pl-10">
                    <div class="h2 font-bold">About</div>
                    <div>Learn about the people behind Task Tots</div>
                </ListBoxItem>
                <ListBoxItem bind:group={valueSingle} name="medium" value="blog" class="pl-10">
                    <div class="h2 font-bold">Blog</div>
                    <div>Check out our most recent Blog posts</div>
                </ListBoxItem>
                <ListBoxItem bind:group={valueSingle} name="medium" value="tools" class="pl-10">
                    <div class="h2 font-bold">Lorem Ipsum</div>
                    <div>TBD some other promotional card</div>
                </ListBoxItem>
            </ListBox>
        </div>
    </div>

    <div class="card bg-gradient-to-br variant-gradient-primary-secondary rounded-3xl w-1/2 flex flex-col">
        <header class="card-header bg-surface-600 rounded-t-3xl py-8 h2 font-bold">About</header>
        <div class="flex-grow flex items-center justify-center px-10 py-10">
            <Aboutcard />
        </div>
    </div>


</div>