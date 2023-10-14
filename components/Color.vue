<template>
    <div v-if="colors.length !== 0" class="h-full flex items-center -space-x-2 overflow-hidden">
        <div v-if="colors.length > 0" class="inline-block h-5 w-5 rounded-full ring-2 ring-white"
            :style="{ backgroundColor: colors[0] }">
        </div>
        <div v-if="colors.length > 1" class="inline-block h-5 w-5 rounded-full ring-2 ring-white"
            :style="{ backgroundColor: colors[1] }"></div>
        <div v-if="colors.length > 2 && colors.length < 4" class="inline-block h-5 w-5 rounded-full ring-2 ring-white"
            :style="{ backgroundColor: colors[2] }"></div>
        <div v-if="colors.length > 3" class="inline-block h-5 w-5 rounded-full ring-2 ring-white bg-slate-400">
            <div class="flex justify-center items-center h-full text-white text-xs">
                +{{ colors.length - 2 }}
            </div>
            >

        </div>
    </div>
</template>

<script setup>

const { colors } = defineProps({
    colors: Array
})

</script>