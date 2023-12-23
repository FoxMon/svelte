<script>
	import Router from "svelte-spa-router"

	import Home from "./pages/Home.svelte";
	import About from "./pages/About.svelte"
	import Form from "./pages/Form.svelte";

	import Header from "./components/Header.svelte";

	const routes = {
		"/": Home,
		"/about": About,
		"/form": Form
	}
</script>

<main>
	<Header />

	<Router {routes} />
</main>
