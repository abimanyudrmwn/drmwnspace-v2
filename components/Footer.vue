<template>
<footer class="bg-white">
    <div class="w-full max-w-screen-xl mx-auto p-4 md:py-8">
        <div class="sm:flex sm:items-center sm:justify-between">
            <a href="https://flowbite.com/" class="flex items-center mb-4 sm:mb-0">
                <img src="https://chaserlazercom.vercel.app/logo.svg" class="h-8 mr-3" alt="Flowbite Logo" />
            </a>
            <div class="bg-blue-100 justify-between flex py-1 px-3 rounded-full items-center">
                <div class="mr-1 animate-pulse">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-headset" viewBox="0 0 16 16">
                        <path d="M8 1a5 5 0 0 0-5 5v1h1a1 1 0 0 1 1 1v3a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V6a6 6 0 1 1 12 0v6a2.5 2.5 0 0 1-2.5 2.5H9.366a1 1 0 0 1-.866.5h-1a1 1 0 1 1 0-2h1a1 1 0 0 1 .866.5H11.5A1.5 1.5 0 0 0 13 12h-1a1 1 0 0 1-1-1V8a1 1 0 0 1 1-1h1V6a5 5 0 0 0-5-5z"/>
                    </svg>
                </div>
                <div class="mr-1">
                    <p class="font-normal">Recent Listening </p>
                </div>
                <p class="font-light"><span class="font-bold">{{ track.name }}</span> by <span class="font-bold">{{ track.artist }}</span></p>
            </div>
        </div>
        <hr class="my-6 border-gray-200 sm:mx-auto lg:my-8" />
        <span class="block text-sm text-gray-500 sm:text-center">© 2023 <a href="/" class="hover:underline">abimanyudrmwn</a>. All Rights Reserved.</span>
    </div>
</footer>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            track: {}
        };
    },
    async mounted() {
        const apiKey = '8c060f3de34eafed794903a84e501997';
        const username = 'abimanyudrmwn';
        const url = `https://ws.audioscrobbler.com/2.0/?method=user.getrecenttracks&user=${username}&api_key=${apiKey}&format=json`;
        try {
            const response = await axios.get(url);
            const trackData = response.data.recenttracks.track[0];
            const track = {
                name: trackData.name,
                artist: trackData.artist['#text'],
                image: trackData.image[2]['#text']
            };
            this.track = track;
        } catch (error) {
            console.log(error);
        }
    }
}
</script>