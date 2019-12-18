<script>
    import Column from './Column.svelte';

    let columns = [
        [],
        [],
        []
    ];

    const addItem = (column) => {
        columns[column] = columns[column].concat({
            content: "You can start editing by clicking here... 🙌"
        });
    }
</script>

<main class="app">
    <img src="assets/images/svelte-board.png" alt="logo" class="logo" />

    <section class="grid">
        <div class="actions">
            <button on:click={() => addItem(0)}>Went well <img src="assets/images/add.png" alt="add" /></button>
            <button on:click={() => addItem(1)}>To improve <img src="assets/images/add.png" alt="add" /></button>
            <button on:click={() => addItem(2)}>Action items <img src="assets/images/add.png" alt="add" /></button>
        </div>

        <div class="columns">
            <div class="column column-1">
                {#each columns[0] as item}
                    <Column content={item.content} />
                {/each}
            </div>


            <div class="column column-2">
                {#each columns[1] as item}
                    <Column content={item.content} />
                {/each}
            </div>

            <div class="column column-3">
                {#each columns[2] as item}
                    <Column content={item.content} />
                {/each}
            </div>
        </div>
    </section>
</main>