<template>
    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Homepage
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        <div class="flex wrap">
                            <product
                                v-for="product in products"
                                :key="product.id"
                                :product="product"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </BreezeAuthenticatedLayout>
</template>

<script>
import { Head, Link } from "@inertiajs/inertia-vue3";
import BreezeAuthenticatedLayout from "@/Layouts/Authenticated.vue";
import Product from "@/Components/Front/Product.vue";

export default {
    components: {
        BreezeAuthenticatedLayout,
        Head,
        Link,
        Product,
    },
    props: {
        canLogin: Boolean,
        canRegister: Boolean,
        products: Array,
    },
};
</script>
