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
            &__left {
                display: flex;
                flex-direction: column;
                & img {
                    max-width: var(--logo-size);
                    object-fit: contain;
                }
            }
            &__right {
                display: flex;
                flex-direction: column;
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
            flex-direction: column;
            justify-content: center;
            padding: 0.5rem 0;
            & .large-heading {
                font-weight: 500;
                color: var(--brand-main);
                font-size: 2rem;
            }
            & .sub-heading {
                font-weight: 500;
            }
        }
    }
    .alert-box {
        width: 100%;
        display: flex;
        justify-content: center;
        &__inner {
            width: var(--content-size);
            display: flex;
            align-items: center;
            & h2 {
                font-weight: 300;
                color: var(--brand-warning);
                font-size: var(--alert-size);
            }
        }
    }
</style>

<nav class="nav">
    <div class="nav__inner">
        <div class="nav__inner__left">
            <img
                src="https://ik.imagekit.io/usam13ogl7u/usasmbiz-logo_RVYr-FvNM9.png"
                alt="logo" />
        </div>
        <div class="nav__inner__right">
            <span>PRB Control #3245-0406</span>
            <span>Expiration Date: 11/30/2023</span>
        </div>
    </div>
</nav>
<div class="title-bar">
    <div class="title-bar__content">
        <span class="large-heading">COVID-19 Marketing Assistance</span>
        <span class="sub-heading">Marketing Relief for America’s Small
            Businesses and Private Non-profits</span>
    </div>
</div>
<div class="alert-box">
    <div class="alert-box__inner">
        <h2>COVID-19 MARKETING ASSISTANCE APPLICATION</h2>
    </div>
</div>
