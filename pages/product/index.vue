<template>
    <div class="mx-auto max-w-2xl px-4 py-4 sm:px-6 sm:py-4 lg:max-w-7xl lg:px-8">
        <div class="mt-6 grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-5 xl:gap-x-8">
            <div v-for="product in products" :key="product.id" class="group relative">
                <div
                    class="aspect-h-1 aspect-w-1 w-full overflow-hidden rounded-md lg:aspect-none group-hover:opacity-75 lg:h-72">
                    <img :src="product.image" :alt="product.title.EN"
                        class="h-full w-full object-contain object-center lg:h-full lg:w-full" />
                </div>
                <div class="mt-4 flex flex-col justify-between">

                    <h3 class="text-sm text-gray-700">
                        <a :href="product.href">
                            <span aria-hidden="true" class="absolute inset-0" />
                            {{ product.title.EN }}
                        </a>
                    </h3>
                    <div class="flex justify-between">
                        <p>{{ product.brand_alias }}</p>
                        <Rating :rating="Math.round(parseFloat(product.rating))" />
                    </div>
                    <div class="flex flex-col">
                        <div v-if="product.price.original_value !== product.price.value" class="oled-price">
                            {{ product.price.original_value }} {{ product.price.currency }}
                        </div>
                        <div class="flex justify-between">
                            <div>
                                {{ product.price.value }} {{ product.price.currency }}
                            </div>
                            <div>
                                <Color :colors="product.colors" />
                            </div>
                        </div>
                    </div>


                </div>
            </div>
        </div>
    </div>
</template>
  
<script setup>
const { data } = await useFetch('/api/posts')
const products = ref(data.value)
</script>

<style scoped>
* {
    outline: slateblue solid 1px;
}

.oled-price {
    text-decoration-line: line-through;
}
</style>
