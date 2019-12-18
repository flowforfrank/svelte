<script>
    import { fly } from 'svelte/transition';

    const remove = (e) => e.target.parentElement.remove();

    const clap = (e) => {
        const numberOfClaps = parseInt(e.target.dataset.claps, 10)
        
        e.target.dataset.claps = numberOfClaps + 1;
        e.target.innerText = `👏x${numberOfClaps + 1}`;
    }

    export let content;
</script>

<div class="item" in:fly="{{ y: 200, duration: 300 }}">
    <span class="content" contenteditable>{content}</span>

    <button class="remove" on:click={remove}>x</button>
    <span class="claps" on:click={clap} data-claps="0">👏x0</span>
</div>