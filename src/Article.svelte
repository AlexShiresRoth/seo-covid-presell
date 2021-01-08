<script>
    import Icon from "svelte-awesome";
    import { file, building } from "svelte-awesome/icons";
    import DropBox from "./DropBox.svelte";
</script>

<style type="text/scss">
    /* your styles go here */
    .section {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
        margin-bottom: 4rem;
        padding-bottom: 4rem;
        &__content {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: var(--content-size);
            border: 1px solid #eee;
            padding-bottom: 2rem;
            & .icon-heading {
                width: 100%;
                display: flex;
                align-items: center;
                justify-content: center;
                border-bottom: 1px solid #eee;
                padding: 1rem 0;
                &__row {
                    width: var(--content-size);
                    display: flex;
                    justify-content: space-between;
                    margin: 1rem 0;
                    position: relative;

                    & .line-through {
                        width: 100%;
                        position: absolute;
                        height: 3px;
                        background: var(--brand-main);
                        display: block;
                        z-index: 0;
                        top: 50%;
                    }
                    & .icon-container {
                        border-radius: 50%;
                        height: var(--icon-container-size);
                        width: var(--icon-container-size);
                        box-shadow: 0 1px 30px #66666625;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        z-index: 2;
                        background: #fff;
                        border: 1px solid #09154027;
                        & svg {
                            color: #eee;
                        }
                    }
                    & .icon-container:nth-child(2) {
                        background: var(--brand-main);
                    }
                }
            }
            & .text {
                margin-top: 1rem;
                width: 90%;
                & h3 {
                    color: var(--brand-main);
                    font-size: 1.5rem;
                }
                & p {
                    color: #333;
                    line-height: 1.5;
                    font-size: var(--text-size);
                }
            }
        }
    }
</style>

<section class="section">
    <div class="section__content">
        <div class="icon-heading">
            <div class="icon-heading__row">
                <div class="line-through" />
                <div class="icon-container">
                    <Icon data={file} scale="1.5" style="color: #fff" />
                </div>
                <div class="icon-container">
                    <Icon data={building} scale="1.5" style="color: #999" />
                </div>
                <div class="icon-container">
                    <Icon data={file} scale="1.5" style="color: #999" />
                </div>
                <div class="icon-container">
                    <Icon data={building} scale="1.5" style="color: #999" />
                </div>
            </div>
        </div>
        <div class="text">
            <h3>This is a special small business alert.</h3>
            <p>
                Due to Covid-19 and the closure of businesses worldwide,
                <strong>a special relief program</strong>
                has been established
                <strong>to help American businesses survive</strong>
                these tougher than ever times by helping them establish new
                marketing channels at hugely discounted rates. This special
                relief program is intended to
                <strong>bring more customers to local businesses suffering from
                    the effects of Covid-19</strong>.
            </p>
            <p>
                The enactment of this long-awaited Small Business program is
                finally here, and one that is sure to help boost America’s
                struggling small businesses,
                <strong>some businesses may report up to 3 new customers coming
                    in each day</strong>
                thanks to the new digital marketing programs now offered in
                conjunction with relief for small businesses.
            </p>
            <p>
                Businesses looking for new streams of customers
                <strong>may be eligible for subsidized marketing services</strong>
                and are encouraged to
                <u>apply today while space is available</u>, and this program is
                in force. Those who need new customers for their businesses to
                survive will find that these new programs are exactly what they
                have been missing.
            </p>
            <p>
                Businesses who have taken advantage of this special promotion
                have reported positive results from the first few weeks of the
                programs availability.
            </p>
            <p>
                The highly discounted services are
                <strong>only offered while space is available</strong>, and it
                <u>is expected to fill up very fast!</u>
            </p>
            <p>
                To
                <strong>apply for this program</strong>
                please select your state below
            </p>
            <DropBox />
        </div>
    </div>
</section>
