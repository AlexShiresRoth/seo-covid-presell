<script>
	import Article from "./Article.svelte";
	import Navbar from "./Navbar.svelte";
</script>

<style type="text/scss">
	:root {
		--brand-main: #091540;
		--brand-text-dark: #3d518c;
		--brand-text-light: #f1e9db;
		--brand-warning: #a2242280;
		--content-size: 70%;
	}
</style>

<Navbar />
<main>
	<Article />
</main>
