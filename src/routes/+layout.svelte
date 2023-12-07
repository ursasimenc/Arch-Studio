<script>
	import "$lib/styles/main.css";
	import Navbar from "$lib/components/Navbar/Navbar.svelte";
	import Footer from "$lib/components/Footer/Footer.svelte";
</script>

<Navbar />
<slot />
<Footer />
