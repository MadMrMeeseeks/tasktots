<script lang="ts">
    import { Stepper, Step } from '@skeletonlabs/skeleton';
    import { goto } from '$app/navigation';
    import { page } from '$app/stores';


    let currentStep = 0; // Default step

    // Set current step based on route
    $page.route.id === '/login' && (currentStep = 0);
    $page.route.id === '/login/username' && (currentStep = 1);
    $page.route.id === '/login/photo' && (currentStep = 2);

    function onStepHandler(e: {detail: {state: {current: number, total: number}, step: number}}): void {
        switch(e.detail.state.current){
            case 0:
                goto('/login');
                break;
            case 1:
                goto('/login/username');
                break;
            case 2:
                goto('/login/photo');
                break;
        }
    }
</script>



<div class="flex items-center justify-center mt-20">
    <div class="w-full card p-4 text-token max-w-2xl">
        <Stepper start={currentStep} on:step={onStepHandler}>
            <Step>
                <div slot="header" class="text-center">Login</div>
                <div class="flex justify-center items-center">
                    <slot />
                </div>
            </Step>
            <Step>
                <div slot="header" class="text-center">Create Username</div>
                <div class="flex justify-center items-center">
                    <slot />
                </div>
            </Step>
            <Step>
                <div slot="header" class="text-center">Upload Photo</div>
                <div class="flex justify-center items-center">
                    <slot />
                </div>
            </Step>
        </Stepper>
    </div>
</div>





