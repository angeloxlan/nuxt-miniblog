<template>
    <div class="layout-default">
        <header>
            <menu>
                <NuxtLink to="/">TheBlog</NuxtLink>
                <NuxtLink to="/">Home</NuxtLink>
            </menu>
        </header>
        <Nuxt />
    </div>
</template>

<script>
export default {
    name: 'LayoutDefault',
}
</script>

<style lang="scss" scoped>
.layout-default {
    @apply min-h-full;
    header {
        @apply sticky absolute top-0 z-10;
        background-color: rgba(228,230,236,0.9);

        menu {
            @apply m-auto flex justify-between items-center w-full max-w-5xl px-4 py-6;
        }
        .brand {
            @apply font-bold text-2xl;
        }
    }
}
</style>
