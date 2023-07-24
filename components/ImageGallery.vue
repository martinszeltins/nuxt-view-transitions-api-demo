<template>
    <section class="grid grid-cols-4 md:grid-cols-6 gap-1">
        <article v-for="movie in movies.results">
            <NuxtLink :to="`/movie/${movie.id}`" @click.native="active = movie.id">
                <NuxtImg
                    v-if="movie.poster_path"
                    width="400"
                    height="600"
                    :src="`/tmdb${movie.poster_path}`"
                    class="w-full h-full object-cover rounded"
                    :class="{ '[view-transition-name:selected-film]': active === movie.id }"
                />
            </NuxtLink>
        </article>
    </section>
</template>

<script setup>
    const config = useRuntimeConfig()

    const { data: movies } = await useFetch('/tmdb/tv/popular', {
        baseURL: config.public.imageApi,
            query: {
            page: 1,
            language: 'en',
        },
    })

    const active = useState()
</script>
