<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export const dispatch = createEventDispatcher<{
		foo: { id: number; name: string };
	}>();
</script>
