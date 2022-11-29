<template>
    <div class="article-card">
        <figure>
            <img :src="cover" alt="thumbnail" />
        </figure>
        <div class="description">
            <p class="author">{{ author }} - <small>{{ date }}</small></p>
            <h3>{{ title }}</h3>
            <p class="short">{{ description }}</p>
        </div>
    </div>
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

<style lang="scss">
.article-card {
    @apply rounded-lg bg-white;

    figure {
        @apply rounded-lg overflow-hidden max-h-96;
    }

    .description {
        @apply flex flex-col justify-around p-2;

        .author {
            @apply text-slate-400 font-semibold;
        }

        h3 {
            @apply text-3xl font-bold;
        }
        
        .short {
            @apply text-slate-400 font-semibold;
        }
    }
}
</style>
