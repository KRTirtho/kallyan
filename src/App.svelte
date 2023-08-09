<script lang="ts">
	import { Router, Route } from 'svelte-routing';
	import Configure from './pages/configure.svelte';
</script>

<main>
	<Router url="/configure">
		<div class="p-2">
			<Route path="/configure"><Configure /></Route>
		</div>
	</Router>
</main>
