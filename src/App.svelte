<script>
	import Article from "./Article.svelte";
	import Navbar from "./Navbar.svelte";
</script>

<style type="text/scss">
	:root {
		--brand-main: #091540;
		--brand-text-dark: #3d518c;
		--brand-text-light: #f1e9db;
		--brand-warning: #e20f0b;
		--content-size: 75%;
		--text-size: 1.2rem;
		--icon-container-size: 5rem;
	}
	@media screen and (max-width: 900px) {
		:root {
			--content-size: 90%;
			--text-size: 1rem;
			--icon-container-size: 2.5rem;
		}
	}
</style>

<Navbar />
<main>
	<Article />
</main>
