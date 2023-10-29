<template>
    <a href="index.html" class="logo"><img :src="logo" alt="logo"></a>
    <nav class="nav">
        <ul class="nav__list"> 
            <li><a href="index.html">Home</a></li>
            <li><a href="#">Project</a></li>
            <li><a href="blog.html">Blog</a></li>
        </ul>
    </nav>
</template>

<script>
    export default {
        data() {
            return {
                logo: require('@/assets/images/logo__img.svg'),
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>