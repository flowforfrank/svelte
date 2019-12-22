<script>
    import { fly } from 'svelte/transition';

    let claps = 0;

    const remove = (e) => e.target.parentElement.remove();
    const clap = (e) => claps++;

    export let content;
</script>

<div class="item" in:fly="{{ y: 200, duration: 300 }}">
    <span class="content" contenteditable>{content}</span>

    <button class="remove" on:click={remove}>x</button>
    <span class="claps" on:click={clap}>👏x{claps}</span>
</div>