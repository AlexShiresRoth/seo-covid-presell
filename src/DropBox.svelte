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
        setTimeout(() => loadingState.update(() => false), 3000);
        setTimeout(
            () =>
                (window.location.href =
                    "https://29dollarseo.com?promo=PC&subid1={transaction_id}"),
            5000
        );
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
</script>

<style type="text/scss">
    /* your styles go here */
    .loading_container {
        display: flex;
        align-items: center;
        & .loader {
            margin-right: 1rem;
            height: 2rem;
            width: 2rem;
            border: 2px solid transparent;
            border-top: 2px solid var(--brand-main);
            border-bottom: 2px solid var(--brand-main);
            border-radius: 50%;
            animation: rotate 0.5s linear infinite;
        }
    }
    .redirect {
        display: flex;
        margin: 2rem 0;
    }
    .redirect-btn {
        padding: 1rem;
        min-width: 15rem;
        max-width: 100%;
        background: var(--brand-main);
        color: #fff;
        border-radius: 3px;
        border: 0;
        text-decoration: none;
        transition: all 0.3s ease;
        &:hover {
            box-shadow: 0 1px 50px rgba(238, 238, 238, 0.534);
            background: lighten(#091540, 5%);
        }
    }
    @keyframes rotate {
        100% {
            transform: rotate(360deg);
        }
    }
</style>

<div class="dropbox-container">
    <div class="dropbox">
        <select
            on:blur={(e) => selectState(e)}
            on:change={(e) => selectState(e)}
            value={statesJSON[selectedState]}>
            <option>Select Your State</option>
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
                <strong>Congratulations</strong>…. There are still open spots in
                <strong>{statesJSON[stateIsSelected].name}</strong>
                … Please hold while we redirect you to the selected agency in
                that area.
            </p>
        {/if}
        <div class="redirect">
            <a
                href={`https://29dollarseo.com?promo=PC&subid1={transaction_id}`}
                class="redirect-btn">Click Here To Redirect</a>
        </div>
    </div>
</section>
