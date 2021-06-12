<script>
	import { Router, Link, Route } from "svelte-navigator";
	import Tailwind from "./Tailwind.svelte";
</script>

<Tailwind/>

<Router>
	<div class="p-8">
		<nav class="flex justify-around">
			<Link to="/">Home</Link>
			<Link to="about">About</Link>
			<Link to="blog">Blog</Link>
		</nav>
	
		<main class="mt-8">
			<Route path="/">
				<h1 class="outline-none text-7xl text-center ring-pink-600 text-red-700">Home</h1>
			</Route>
	
			<Route path="about">
				<h1 class="outline-none text-7xl text-center text-red-700">About</h1>
			</Route>
			
			<Route path="blog/*">
				<Route path="/">
					<h1 class="outline-none text-7xl text-center text-red-700">Blog</h1>
					<Link to="1">Blog 1</Link>
					<Link to="2">Blog 2</Link>
				</Route>
				<Route path=":id" let:params>
					<h1 class="outline-none text-7xl text-center text-red-700">Blog {params.id}</h1>
				</Route>
			</Route>
		</main>
	</div>
</Router>