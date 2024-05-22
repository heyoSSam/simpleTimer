<script lang="ts" setup>

</script>

<template>
        <div class="absolute top-1/2 left-1/2 -translate-x-2/4 -translate-y-2/4 w-max p-5 border-solid border-2 border-black text-center">
            <div class="">
                <p>STOP</p>
                <button @click="$emit('close-notice')" class="border-solid border-white border-2 px-3 py-1 rounded-lg bg-lime-400 text-white">Ok</button>
            </div>
        </div>
</template>
