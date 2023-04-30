<script setup lang="ts">
const { data: posts } = await useAsyncData('posts', () =>
    queryContent('/blog').find()
)
</script>

<template>
    <main class="container mt-16 mb-20">
        <div class="grid grid-cols-1 gap-6 mx-3 sm:grid-cols-2 sm:mx-20">
            <div v-for="post in posts" :key="post._id" class="bg-gray-100 py-10 px-10 rounded-lg">
                <p class="text-gray-600 mb-4"> {{ post.createdAt }}</p>
                <h1 class="text-3xl font-bold text-black">{{ post.title }}</h1>
                <p class="text-gray-600 mb-4 mt-3">{{ post.description }}</p>
                <div class="mt-8"></div>
                <a class="bg-blue-600 text-white py-2 px-3 rounded-md font-bold" :href="post._path">Read More →</a>
            </div>
        </div>
    </main>
</template>