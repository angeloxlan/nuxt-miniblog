<template>
    <NuxtLink :to="slug" class="last-article-card">
        <figure>
            <img :src="cover" alt="thumbnail" />
        </figure>
        <div class="description">
            <p class="author">
                {{ author }} - <small>{{ date }}</small>
            </p>
            <h3>{{ title }}</h3>
            <p class="short">{{ description }}</p>
        </div>
    </NuxtLink>
</template>

<script>
export default {
    props: {
        slug: {
            type: String,
            default: '',
        },
        title: {
            type: String,
            default: '',
        },
        author: {
            type: String,
            default: '',
        },
        date: {
            type: Date,
            default: '',
        },
        cover: {
            type: String,
            default: '',
        },
        description: {
            type: String,
            default: '',
        },
    },
}
</script>

<style lang="scss" scoped>
.last-article-card {
    @apply flex justify-between rounded-lg bg-white hover:scale-105 transition;

    figure {
        @apply rounded-lg overflow-hidden max-h-96;
    }

    .description {
        @apply flex flex-col justify-around w-8/12 px-6;

        .author {
            @apply text-slate-400 font-semibold;
        }

        h3 {
            @apply text-5xl font-bold;
        }

        .short {
            @apply text-slate-400 font-semibold;
        }
    }
}
</style>
