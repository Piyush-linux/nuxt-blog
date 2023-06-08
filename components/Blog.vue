<template>
    <div class="">
        <NuxtLink :to="props.path" class="h-90 col-span-1 m-auto min-h-full cursor-pointer overflow-hidden rounded-lg pb-2 shadow-lg transition-transform duration-200 hover:translate-y-2">
            <a href="#" class="block h-full w-full">
                <img class="max-h-40 w-full object-cover" alt="featured image" src="https://images.unsplash.com/photo-1660241588741-d653d53348fa?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHw5fHx8ZW58MHx8fHw%3D&auto=format&fit=crop&w=500&q=60" />
                <div class="w-full bg-white p-4">
                    <p class="text-base font-medium text-indigo-500"> {{ props.tit }} </p>
                    <p class="text-sm text-gray-500">{{ props.des }}</p>
                    <div class="justify-starts mt-4 flex flex-wrap items-center">
                        <div class="mr-2 mt-1 rounded-2xl bg-blue-100 py-1.5 px-4 text-xs text-gray-600">#js</div>
                        <div class="mr-2 mt-1 rounded-2xl bg-blue-100 py-1.5 px-4 text-xs text-gray-600">#icefactory</div>
                    </div>
                </div>
            </a>
        </NuxtLink>
    </div>
</template>

<script setup>
	const props = defineProps(['tit','des','path'])
</script>