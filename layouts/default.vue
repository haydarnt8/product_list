<template>
    <main class="flex flex-col justify-center">
        <div class="h-[30vh]  flex flex-col gap-7 justify-center items-center">
            <h1 class="text-5xl font-bold">Miswag New Arrivals</h1>
            <p>
                Stay Ahead of the Curve with Miswag's Fresh Arrivals!
            </p>
        </div>
        <CategoryNav />
        <slot />

        <button @click="show = !show" class="bg-black text-white p-3">
            show
        </button>

        <div v-if="show" v-html="adiv"></div>


    </main>
</template>

<script setup>
const router = useRouter()
const show = ref(false)
const adiv = "<div class='h-20 w-screen bg-red-500'></div>"

onMounted(() => {
    // console.log('mounted')
    // router.push({ name: 'product-id', params: { id: 1 } })
    // router.push({ path: '/product/1' })
})
</script>

