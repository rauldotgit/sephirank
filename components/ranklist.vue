<template>
    <div class="w-full max-w-3xl px-12 lg:px-8">
        <div class="px-6 pt-12 pb-24">
            <div class="mx-auto max-w-2xl text-center">
                <p class="text-base font-semibold leading-7 text-blue-500">Aktuelle Rangliste</p>
                <h2 class="mt-2 text-4xl font-bold tracking-tight text-gray-100 sm:text-6xl">Smash Or Pass</h2>
                <!-- <p class="mt-6 text-lg leading-8 text-gray-600">Anim aute id magna aliqua ad ad non deserunt sunt. Qui
                    irure qui lorem cupidatat commodo. Elit sunt amet fugiat veniam occaecat fugiat aliqua.</p> -->
            </div>
        </div>
        <ul role="list" class="flex flex-col divide-y divide-gray-100 gap-4">
            <li v-for="person in people" :key="person.rank"
                class="relative flex justify-between gap-x-6 py-5 px-8 bg-white bg-opacity-90 rounded-md ring-1 ring-slate-400">
                <div class="flex items-center justify-between w-full gap-x-4">
                    <div class="flex items-center gap-5">
                        <img class="h-12 w-12 flex-none" :src="person.icon" alt="" />
                        <p class="text-2xl font-semibold leading-6 text-gray-900">
                            {{ person.name }}
                        </p>
                    </div>
                    <p class="text-xl font-bold font-sans">{{ person.rank }}. Rang</p>

                </div>
                <!-- <div class="flex shrink-0 items-center gap-x-4">
                    <div class="hidden sm:flex sm:flex-col sm:items-end">
                        <p class="text-sm leading-6 text-gray-900">{{ person.role }}</p>
                        <p v-if="person.lastSeen" class="mt-1 text-xs leading-5 text-gray-500">
                            Last seen <time :datetime="person.lastSeenDateTime">{{ person.lastSeen }}</time>
                        </p>
                        <div v-else class="mt-1 flex items-center gap-x-1.5">
                            <div class="flex-none rounded-full bg-emerald-500/20 p-1">
                                <div class="h-1.5 w-1.5 rounded-full bg-emerald-500" />
                            </div>
                            <p class="text-xs leading-5 text-gray-500">Online</p>
                        </div>
                    </div>
                    <ChevronRightIcon class="h-5 w-5 flex-none text-gray-400" aria-hidden="true" />
                </div> -->
            </li>
        </ul>
    </div>
</template>

<script setup>
import { ChevronRightIcon } from '@heroicons/vue/20/solid'
import contestants from '@/server/assets/contestants.json'

const people = Object.values(contestants).sort((a, b) => a.rank - b.rank)
</script>