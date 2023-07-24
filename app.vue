<template>
    <nav class="p-4 md:px-6 bg-black text-white">
        <ul class="flex justify-between">
            <NuxtLink to="/" target="">
                Nuxt View Transitions Demo
            </NuxtLink>

            <img class="h-5" src="https://nuxt.com/assets/design-kit/logo/full-logo-green-light.svg" />
        </ul>
    </nav>

    <main class="md:p-6 p-4">
        <NuxtPage />
    </main>
</template>
