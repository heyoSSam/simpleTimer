<script lang="ts" setup>

</script>

<template>
    <div class="flex-grow flex flex-col">
        <div class="my-auto">
            <div class="flex justify-center content-center">
                <BlockTime :time="24" :title="'days'"/>
                <p class="text-3xl my-auto mx-3"> : </p>
                <BlockTime :time="24" :title="'hours'"/>
                <p class="text-3xl my-auto mx-3"> : </p>
                <BlockTime :time="24" :title="'minutes'"/>
                <p class="text-3xl my-auto mx-3"> : </p>
                <BlockTime :time="24" :title="'seconds'"/>
            </div>

            <div class="mx-auto mt-5">
                <button class="w-screen mx-auto ">Start</button>
            </div>
        </div>
    </div>
    


</template>
