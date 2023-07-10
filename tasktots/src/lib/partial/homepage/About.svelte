<script>
    import {ListBox, ListBoxItem} from "@skeletonlabs/skeleton";


    let valueSingle = 'books';
</script>


<div class="flex justify-center space-x-20 mt-32">
    <div class="flex-col justify-center space-y-2 items-center max-w-md">
        <div>
            <h1 class="h1 text-5xl">
                <span class="text-white">Designed to Make Achieving Goals Fun!</span>
            </h1>
            <h1 class="h4">
                <span class="text-white">Task Tot helps you set goals for your children and to discover new ways to build the skills they need to succeed</span>
            </h1>
        </div>
        <div>
            <ListBox>
                <ListBoxItem bind:group={valueSingle} name="medium" value="books">Books</ListBoxItem>
                <ListBoxItem bind:group={valueSingle} name="medium" value="movies">Movies</ListBoxItem>
                <ListBoxItem bind:group={valueSingle} name="medium" value="tv">TV</ListBoxItem>
            </ListBox>
        </div>
    </div>
    <div class="card p-4 max-w-md flex justify-center items-center">
        <div class="flex justify-center items-center">
            <div class="grid place-items-center">
                <img src="/tempadmin.png/" alt="Description of the image">
            </div>
        </div>
    </div>
</div>