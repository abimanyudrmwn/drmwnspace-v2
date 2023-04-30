<template>
  <main>
    <div class="flex justify-center mt-16">
        <div class="w-full bg-white rounded-xl">
            <div class="p-3 sm:p-28">
                <h1 class="font-medium text-4xl text-center text-black tracking-wide">Hi, I'am Abimanyu Darmawan</h1>
                <h1 class="font-bold text-4xl text-center text-black tracking-wide">Frontend Developer & Graphic Designer</h1>
                <p class="text-center text-black text-opacity-70 tracking-wide mx-3 sm:mx-20 mt-3">I embraced the concept of unlimited creativity, allowing my ideas to flourish without the constraints of boundaries.</p>
                <ul class="flex justify-center mt-16 underline font-semibold">
                  <li class="mx-2 hover:text-blue-800"><a href="#">Instagram→</a></li>
                  <li class="mx-2 hover:text-blue-800"><a href="#">Github→</a></li>
                  <li class="mx-2 hover:text-blue-800"><a href="#">Dribbble→</a></li>
                </ul>
            </div>
        </div>
    </div>
    <ServicesCard/>
  </main>
</template>

<script setup>
useHead({
  title: 'abimanyudrmwn',
  meta: [
    { name: 'description', content: 'My amazing site.' }
  ],
})
</script>