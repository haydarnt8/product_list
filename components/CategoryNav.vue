<template>
    <div 
    
    class="flex justify-evenly items-center ">
        <NuxtLink v-for="c in categories" 
        :to="`/product/${c.id}`"
        :key="c.id" class="p-2 rounded-lg"
            :class="{'text-black': id != c.id, }">
            <h3>{{ c.name }}</h3>
        </NuxtLink>
    </div>
</template>
<script setup>

const { params: { id } } = useRoute()

const categories = ref([
    {
        id: 1,
        name: "Smartphones",
    },
    {
        id: 2,
        name: "Screen Protectors",
    },
    {
        id: 3,
        name: "Mobile Covers",
    },
    {
        id: 4,
        name: "Mobile Covers",
    },
    {
        id: 5,
        name: "Mobile Covers",
    }
])
</script>
<style scoped>
.router-link-active {
    background-color: black;
    color: white;
}

</style>