<script>
    // your script goes here
</script>

<style type="text/scss">
    /* your styles go here */
    .nav {
        width: 100%;
        display: flex;
        justify-content: center;
        padding: 1rem 0;
        &__inner {
            width: var(--content-size);
            display: flex;
            justify-content: space-between;
            align-items: center;
            & span {
                font-weight: 700;
            }
        }
    }
    .title-bar {
        width: 100%;
        background: #eee;
        display: flex;
        justify-content: center;
        align-items: center;
        &__content {
            width: var(--content-size);
            display: flex;
            align-items: center;
            & h1 {
                color: var(--brand-text-dark);
                font-weight: 500;
            }
        }
    }
</style>

<nav class="nav">
    <div class="nav__inner"><span>Covid-19 Marketing Relief</span></div>
</nav>
<div class="title-bar">
    <div class="title-bar__content">
        <h1>This is a special small business alert</h1>
    </div>
</div>
