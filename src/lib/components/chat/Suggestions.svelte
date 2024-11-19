<script lang="ts">
	import Bolt from '$lib/components/icons/Bolt.svelte';
	import { onMount, getContext, createEventDispatcher } from 'svelte';

	const i18n = getContext('i18n');
	const dispatch = createEventDispatcher();

	export let suggestionPrompts = [];
	export let className = '';

	let prompts = [];

	$: prompts = (suggestionPrompts ?? [])
		.reduce((acc, current) => [...acc, ...[current]], [])
		.sort(() => Math.random() - 0.5);
</script>
