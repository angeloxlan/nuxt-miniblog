<template>
    <div class="container">
        <AboutMe />
        <div class="content">
            <LastArticleCard v-bind="recentPost" />
            <main>
                <ArticleCard 
                    v-for="article in postsWithoutMostRecent"
                    :key="article.slug"
                    v-bind="article"
                />
            </main>
        </div>
    </div>
</template>

<script>
export default {
    name: 'IndexPage',
    data() {
        return {
            articles: [
                {
                    title: 'My first post',
                    slug: 'my-first-post',
                    date: new Date(),
                    cover: 'https://via.placeholder.com/700x450',
                },
                {
                    title: 'My second post',
                    slug: 'my-second-post',
                    date: new Date(),
                    cover: 'https://via.placeholder.com/400x300',
                },
                {
                    title: 'My second post',
                    slug: 'my-second-post',
                    date: new Date(),
                    cover: 'https://via.placeholder.com/400x300',
                },
                {
                    title: 'My second post',
                    slug: 'my-second-post',
                    date: new Date(),
                    cover: 'https://via.placeholder.com/400x300',
                },
                {
                    title: 'My second post',
                    slug: 'my-second-post',
                    date: new Date(),
                    cover: 'https://via.placeholder.com/400x300',
                },
            ],
        }
    },
    computed: {
        recentPost() {
            return this.articles[0];
        },
        postsWithoutMostRecent() {
            return this.articles.filter((article, index) => {
                return index !== 0;
            });
        },
    },
}
</script>

<style lang="scss">
.container {
    @apply m-auto;
}
.container .content {
    @apply flex flex-col justify-center items-center gap-6 sm:p-2 md:p-4 lg:p-8 xl:p-16;
    main {
        @apply grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6;
    }
}
</style>
