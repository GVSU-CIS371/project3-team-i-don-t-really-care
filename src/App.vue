<template>
    <div>
        <Beverage
            :isIced="data.currentTemp === 'Cold'"
            :baseChoice="data.currentBase"
            :creamerChoice="data.currentCreamer"
        />

        <ul>
            <li>
                <template v-for="temp in data.temps" :key="temp">
                    <label>
                        <input
                            type="radio"
                            name="temperature"
                            :id="`r${temp}`"
                            :value="temp"
                            v-model="data.currentTemp"
                        />
                        {{ temp }}
                    </label>
                </template>
            </li>
        </ul>

        <div>
            <ul>
                <li v-for="base in data.bases" :key="base.id">
                    <label>
                        <input
                            type="radio"
                            name="base"
                            :value="base.name"
                            v-model="data.currentBase"
                        />
                        {{ base.name }}
                    </label>
                </li>
            </ul>
        </div>

        <div>
            <ul>
                <li v-for="creamer in data.creamers" :key="creamer.id">
                    <label>
                        <input
                            type="radio"
                            name="creamer"
                            :value="creamer.name"
                            v-model="data.currentCreamer"
                        />
                        {{ creamer.name }}
                    </label>
                </li>
            </ul>
        </div>

        <div>
            <ul>
                <li v-for="syrup in data.syrups" :key="syrup.id">
                    <label>
                        <input
                            type="radio"
                            name="syrup"
                            :value="syrup.name"
                            v-model="data.currentSyrup"
                        />
                        {{ syrup.name }}
                    </label>
                </li>
            </ul>
        </div>
    </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { reactive } from "vue";
import { temps, bases, creamers, syrups } from "./stores/beverage";

const data = reactive({
    temps: ["Hot", "Cold"],
    currentTemp: "Hot",
    bases: bases.value,
    currentBase: "Coffee",
    creamers: creamers.value,
    currentCreamer: "No Cream",
    syrups: syrups.value,
    currentSyrup: "No Syrup",
});

function updateBaseChoice() {
    console.log(data.currentBase);
}

function updateSyrupChoice() {
    console.log(data.currentSyrup);
}

function updateCreamerChoice() {
    console.log(data.currentCreamer);
}
</script>

<style lang="scss">
body,
html {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    background-color: #6e4228;
    background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
    list-style: none;
}
</style>
