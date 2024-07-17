<script setup lang="ts">
import DarkModeToggle from '@/Components/DarkModeToggle.vue'
import CreateProductCard from '@/Components/partial/CreateProductCard.vue'

</script>

<template>
    <div class="grid place-items-center h-[100vh]">
        <div class="w-[500px]">
            <div class="flex flex-row justify-between">
                <div class="mb-[50px]" >
                    <h1 class="scroll-m-20 text-4xl font-extrabold tracking-tight lg:text-5xl">
                        Product
                    </h1>
                </div>
                <DarkModeToggle />
            </div>
            <CreateProductCard />
        </div>
    </div>
</template>