<template>
	<IndexPage/>
	<BlogPage/>
	<BlogDetailsPage/>
	<ProjectPage/>
	<ProjectDetailsPage />
</template>

<script>
import IndexPage from './components/IndexPage.vue';
import BlogPage from './components/BlogPage.vue';
import BlogDetailsPage from './components/BlogDetailsPage.vue';
import ProjectPage from './components/ProjectPage.vue';
import ProjectDetailsPage from './components/ProjectDetailsPage.vue';


export default { 
	components: {
		IndexPage,
		BlogPage,
		BlogDetailsPage,
		ProjectPage,
		ProjectDetailsPage
	},
};
</script>

<style lang="scss">
</style>
