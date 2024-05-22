<script lang="ts" setup>
import {ref} from 'vue';

let day = ref(0), hour = ref(0), minute = ref(0), second = ref(0), end = ref(false);

function start() {
    let Interval = setInterval(() => {
        if(day.value == 0 && hour.value == 0 && minute.value == 0 && second.value == 0){
            end.value = true;
            clearInterval(Interval);
        }
        
        else{
            if(second.value == 0 && (minute.value > 0 || hour.value > 0 || day.value > 0)){
                if(minute.value > 0)
                    minute.value--;
                if(hour.value > 0){
                    hour.value--;
                    minute.value = 59;
                }
                if(day.value > 0){
                    day.value--;
                    hour.value = 23;
                    minute.value = 59;
                }
                second.value = 59;
            } else{
                second.value--;
            }
        }
    }, 1000);

    return {day,hour,minute,second};
}
</script>

<template>
    <div class="flex-grow flex flex-col" :class="{'opacity-5' : end}">
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
                <button class="w-screen mx-auto" @click="start">Start</button>
            </div>
        </div>
    </div>

    <div v-if="end">
        <Notification @close-notice="end = !end;"/>
    </div>
    
</template>
