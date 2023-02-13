<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { Link } from '@inertiajs/vue3'



defineProps({
    posts: Object,
})
</script>

<template>
    <Head title="Post" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
<Link class="p-2 bg-slate-600 rounded-lg text-white" :href="route('posts.create')">Tambah Data</Link>

<div class="flex flex-col">
  <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
    <div class="py-2 inline-block min-w-full sm:px-6 lg:px-8">
      <div class="overflow-hidden">
        <table class="min-w-full border text-center">
          <thead class="border-b">
            <tr>
              <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 border-r">
                #
              </th>
              <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 border-r">
                Title
              </th>
              <th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 border-r">
                Body
              </th><th scope="col" class="text-sm font-medium text-gray-900 px-6 py-4 border-r">
                Action
              </th>
            </tr>
          </thead>
          <tbody>
            <tr class="border-b" v-for="post in posts">
              <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900 border-r">{{ post.id }}</td>
              <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap border-r">
                {{ post.title }}
              </td>
              <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap border-r">
                {{ post.body }}
              </td>
              <td class="text-sm text-gray-900 font-light px-6 py-4 whitespace-nowrap border-r">
                <Link :href="route('posts.edit', post.id)" class="p-2 bg-slate-600 rounded-lg text-white">Edit</Link>
                <Link :href="route('posts.destroy', post.id)" method="delete" as="button" class="p-2 bg-red-600 rounded-lg text-white">Delete</Link>

              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</div>
</div>
</div>
    </AuthenticatedLayout>
</template>
