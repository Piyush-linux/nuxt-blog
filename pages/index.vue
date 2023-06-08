<template>
    <div class="">
        <!-- hero -->
        <div class="my-10 mx-auto flex w-screen max-w-screen-lg flex-col rounded-3xl bg-green-50 px-4">
            <p class="mt-20 text-center sm:text-lg font-semibold text-lime-500">Our Blog</p>
            <h1 class="mx-auto mt-2 max-w-3xl text-center text-2xl font-semibold leading-tight sm:text-4xl md:text-5xl">Resources for makers and creaters to learn, sell & Grow</h1>
            <p class="mx-auto hidden sm:block mt-4 max-w-5xl text-center text-gray-500 sm:mt-8 sm:text-lg">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quo quis deleniti minus ab aliquam nemo.</p>
            <div class="mx-auto mt-8 mb-20 flex w-full flex-col space-y-2 sm:w-auto sm:flex-row sm:space-y-0 sm:space-x-6">
                <button class="rounded-full bg-black px-10 py-3 font-medium text-white hover:opacity-80 sm:w-auto">Get Started</button>
                <button class="rounded-full border-2 border-black px-10 py-3 font-medium text-black transition hover:bg-black hover:text-white sm:w-auto">View Pricing</button>
            </div>
        </div>
        <!-- search -->
        <div class="mx-auto flex justify-center">
            <div class="m-10 w-screen max-w-screen-md">
                <div class="flex flex-col">
                    <div class="rounded-xl border border-gray-200 bg-white p-6 shadow-lg">
                        <form class="">
                            <div class="relative w-full flex  items-center justify-between rounded-md">
                                <svg class="absolute left-2 block h-5 w-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <circle cx="11" cy="11" r="8" class=""></circle>
                                    <line x1="21" y1="21" x2="16.65" y2="16.65" class=""></line>
                                </svg>
                                <input type="name" name="search" class="h-12 w-full cursor-text rounded-md border border-gray-100 bg-gray-100 py-4 pr-40 pl-12 shadow-sm outline-none focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50" placeholder="Search by name, type, manufacturer, etc" />
                                <button class="button bg-green-200 h-full p-3">submit</button>
                            </div>
                           <!--  <div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
                                <div class="flex flex-col">
                                    <label for="name" class="text-sm font-medium text-stone-600">Name</label>
                                    <input type="text" id="name" placeholder="Raspberry juice" class="mt-2 block w-full rounded-md border border-gray-100 bg-gray-100 px-2 py-2 shadow-sm outline-none focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50" />
                                </div>
                                <div class="flex flex-col">
                                    <label for="manufacturer" class="text-sm font-medium text-stone-600">Manufacturer</label>
                                    <select id="manufacturer" class="mt-2 block w-full rounded-md border border-gray-100 bg-gray-100 px-2 py-2 shadow-sm outline-none focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50">
                                        <option>Cadberry</option>
                                        <option>Starbucks</option>
                                        <option>Hilti</option>
                                    </select>
                                </div>
                                <div class="flex flex-col">
                                    <label for="date" class="text-sm font-medium text-stone-600">Date of Entry</label>
                                    <input type="date" id="date" class="mt-2 block w-full cursor-pointer rounded-md border border-gray-100 bg-gray-100 px-2 py-2 shadow-sm outline-none focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50" />
                                </div>
                                <div class="flex flex-col">
                                    <label for="status" class="text-sm font-medium text-stone-600">Status</label>
                                    <select id="status" class="mt-2 block w-full cursor-pointer rounded-md border border-gray-100 bg-gray-100 px-2 py-2 shadow-sm outline-none focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50">
                                        <option>Dispached Out</option>
                                        <option>In Warehouse</option>
                                        <option>Being Brought In</option>
                                    </select>
                                </div>
                            </div> -->
                            <!-- <div class="mt-6 grid w-full grid-cols-2 justify-end space-x-4 md:flex">
                                <button class="rounded-lg bg-gray-200 px-8 py-2 font-medium text-gray-700 outline-none hover:opacity-80 focus:ring">Reset</button>
                                <button class="rounded-lg bg-blue-600 px-8 py-2 font-medium text-white outline-none hover:opacity-80 focus:ring">Search</button>
                            </div> -->
                        </form>
                    </div>
                </div>
            </div>
        </div>
        <!-- blogs -->
        <section class="py-20">
            <div class="mx-auto grid max-w-screen-lg grid-cols-1 gap-5 p-5 sm:grid-cols-2 md:grid-cols-3 lg:gap-10">
            	<div v-for="i in data">
	                <Blog :tit="i.title" :des="i.description" :path="i._path" />
	                <!-- {{ i._path }} -->
            	</div>
            </div>
        </section>
    </div>
</template>

<script setup>
	const { data } = await useAsyncData('home', () => queryContent('/blogs').find())
</script>