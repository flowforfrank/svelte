<script>
    import { fly, scale } from 'svelte/transition';

    export let content;
    export let remove;
    export let clap;
</script>

<div class="item" in:fly="{{ y: 200, duration: 300 }}">
    <span class="content" contenteditable>{content}</span>

    <button class="remove" on:click={remove}>x</button>
    <span class="claps" on:click={clap} data-claps="0">👏x0</span>
</div>