<script lang="ts" setup>

</script>

<template>
    <div class="h-screen flex flex-col">
        <header class="flex justify-center">
            <h1 class="text-5xl">Timer ⏰</h1>
        </header>

        <main class="flex-1 flex flex-col">
            <slot/> 
        </main>

        <footer class="w-screen absolute bottom-0">
            <p class="text-center">blablabla</p>
        </footer>
    </div>
</template>

