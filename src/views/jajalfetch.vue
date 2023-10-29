<script setup>
import axios from 'axios';
import { ref } from 'vue';

const endpoint = "https://test.nubaim.my.id/data";
//get data from endpoint
const data = ref(null);
const is_fetched = ref(false);
const getData = async () => {
    try {
        const response = await axios.get(endpoint);
        console.log(response);
        data.value = response.data.animeList;
        is_fetched.value = true;
    } catch (error) {
        console.error(error);
    }
}



getData();

</script>

<template>
    <div class="mt-3 mx-3 grid grid-cols-3 gap-6">
        <div v-if="is_fetched" v-for="e in data" class="flex justify-center">
            <div class="max-w-sm rounded overflow-hidden shadow-lg">
                <img class="" src="https://placewaifu.com/image/200" height="50" alt="Sunset in the mountains">
                <div class="px-2 py-4">
                    <div class="font-bold text-xl mb-2">{{e.title}}</div>
                    <div class="text-gray-700 text-base">
                        {{ e.genre  }}
                    </div>
                    <div class="text-gray-700 text-base">
                        {{ e.rating  }}
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>