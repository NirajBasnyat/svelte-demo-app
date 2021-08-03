<script>
	import Header from './components/Header.svelte';
	import Footer from './components/Footer.svelte';
	import Home from './components/Home.svelte';
	import Login from './components/Login.svelte';
	import ContactUs from './components/ContactUs.svelte';

	import { Router, Route } from 'svelte-routing';

	 export let url = "";
</script>

<Router  url="{url}">
	<Header />

	<div class="container">
		<Route path="/" component={Home} />
		<Route path="/login" component={Login} />
		<Route path="/contact" component={ContactUs} />
	</div>

	<Footer />
</Router>
