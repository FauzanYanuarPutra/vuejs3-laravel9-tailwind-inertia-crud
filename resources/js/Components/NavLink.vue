<script setup>
import { computed } from 'vue';
import { Link } from '@inertiajs/vue3';

const props = defineProps(['href', 'active']);

const classes = computed(() =>
    props.active
        ? 'flex items-center pb-7 flex m-5 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700 mb-2'
        : 'flex items-center pb-7 flex m-5 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700 mb-2'
);
</script>

<template>
    <Link :href="href" :class="classes">
        <slot />
    </Link>
</template>
