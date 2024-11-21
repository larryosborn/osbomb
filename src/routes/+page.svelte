<script>
	import { Bomb } from 'lucide-svelte';
	import BioCard from './(components)/BioCard.svelte';
</script>

<div class="flex h-full items-center justify-center">
	<div class="flex flex-col items-center justify-center gap-5 md:flex-row">
		<Bomb size="128" />
		<BioCard />
	</div>
</div>
