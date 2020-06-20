<script>
	import '../node_modules/uikit/dist/css/uikit.min.css';
	import '../node_modules/uikit/dist/js/uikit.min.js';
	
	import Navbar from './reusables/Navbar.svelte';
	import MainHeader from './reusables/MainHeader.svelte';
	import ArticleList from './reusables/ArticleList.svelte';

</script>

<Navbar />

<main>
	<MainHeader />

	<!-- A list of articles -->
	<ArticleList />

</main>

<style>

</style>