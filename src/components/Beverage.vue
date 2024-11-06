<template>
    <Mug>
        <Cold v-if="isIced" />
        <Hot v-else />
        <Contents>
            <template v-slot:top>
                <Creamer v-if ="creamerChoice" :name="creamerChoice" />
            </template>
            <template v-slot:mid>
                <Syrup v-if ="syrupChoice ":name="syrupChoice" />
            </template>
            <template v-slot:bottom>
                <Base :name="baseChoice" />
            </template>
        </Contents>
    </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
    isIced: boolean;
    baseChoice: string;
    creamerChoice: string;
    syrupChoice: string;
};
defineProps<Props>();
</script>
