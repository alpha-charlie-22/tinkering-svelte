<script>
    // import { onDestroy, onMount } from 'svelte';

    import { fade, scale } from 'svelte/transition';

    import { FeedbackStore } from '../stores';
    import FeedbackItem from './FeedbackItem.svelte'
    // export let feedback = [];

    // const unsubscribe = FeedbackStore.subscribe((data) => feedback = data)

    // onMount(() => {
    //     console.log('mounted')
    // })
    // onDestroy(() => {
    //     console.log('on destroy')
    //     unsubscribe()
    // })
</script>

{#each $FeedbackStore as fb (fb.id)}
<div in:scale out:fade="{{ duration: 700 }}" >
    <FeedbackItem item={fb} />
</div>
{/each}