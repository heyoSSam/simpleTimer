<script lang="ts" setup>
import {ref} from 'vue';

let day = ref(0), hour = ref(0), minute = ref(0), second = ref(0);

function addition(value:number):number {
    return value++;
}
</script>

<template>
    <div class="flex-grow flex flex-col">
        <div class="my-auto">
            <div class="flex justify-center content-center">
                <div>
                    <BlockTime :time="day" :title="'days'"/>
                    <div class="flex justify-center">
                        <button @click="day++" class="text-2xl mx-1">+</button>
                        <button @click="if(day > 0){day--;}" class="text-2xl mx-1">-</button>
                    </div>
                </div>
                <p class="text-3xl my-auto mx-3"> : </p>
                <div>
                    <BlockTime :time="hour" :title="'hours'"/>
                    <div class="flex justify-center">
                        <button @click="hour++" class="text-2xl mx-1">+</button>
                        <button @click="if(hour > 0){hour--;}" class="text-2xl mx-1">-</button>
                    </div>
                </div>
                <p class="text-3xl my-auto mx-3"> : </p>
                <div>
                    <BlockTime :time="minute" :title="'minutes'"/>
                    <div class="flex justify-center">
                        <button @click="minute++" class="text-2xl mx-1">+</button>
                        <button @click="if(minute > 0){minute--;}" class="text-2xl mx-1">-</button>
                    </div>
                </div>
                <p class="text-3xl my-auto mx-3"> : </p>
                <div>
                    <BlockTime :time="second" :title="'seconds'"/>
                    <div class="flex justify-center">
                        <button @click="second++" class="text-2xl mx-1">+</button>
                        <button @click="if(second > 0){second--;}" class="text-2xl mx-1">-</button>
                    </div>
                </div>
                
            </div>

            <div class="mx-auto mt-5">
                <button class="w-screen mx-auto">Start</button>
            </div>
        </div>
    </div>
    


</template>
