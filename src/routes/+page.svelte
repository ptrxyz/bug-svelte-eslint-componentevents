<script lang="ts">
	import type { ComponentEvents } from 'svelte';
	import Comp from './component.svelte';

	type X = ComponentEvents<Comp>['foo'];
	export const x: X | null = null;
</script>
