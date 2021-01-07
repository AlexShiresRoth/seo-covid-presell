<script>
    import { writable } from "svelte/store";
    import { statesJSON } from "./states";

    const selectedState = writable(0);
    const loadingState = writable(false);

    let processing;
    let altprocess;
    let stateIsSelected;

    $: newState = altprocess;

    selectedState.subscribe((stateIndex) => {
        stateIsSelected = stateIndex;
    });

    loadingState.subscribe((loadingBool) => {
        return (processing = loadingBool);
    });

    const setProcessing = () => {
        loadingState.update(() => true);
        setTimeout(() => loadingState.update(() => false), 5000);
    };

    const selectState = (e) => {
        clearTimeout();

        selectedState.update(() => {
            //return the state value
            return e.target.value;
        });

        //manufacture a processing effect
        return setProcessing();
    };

    console.log(newState);
    //TODO figure out why processing happens twice
</script>

<style>
    /* your styles go here */
</style>

<div class="dropbox-container">
    <div class="dropbox">
        <select
            on:blur={(e) => selectState(e)}
            on:change={(e) => selectState(e)}
            value={statesJSON[selectedState]}>
            {#each statesJSON as stateJSON, i}
                <option value={i}>{stateJSON.name}</option>
            {/each}</select>
    </div>
</div>
<section class="section">
    <div class="section__inner">
        {#if processing}
            <div class="loading_container">
                <div class="loader" />
                <p>Loading your results...</p>
            </div>
        {/if}
        {#if !stateIsSelected && !processing}
            <p>Please select your state to check for available spots</p>
        {/if}
        {#if !processing && stateIsSelected}
            <p>
                Congratulations …. There are still open spots in
                {statesJSON[stateIsSelected].name}
                … Please hold while we redirect you to the selected agency in
                that area.
            </p>
        {/if}
    </div>
</section>
