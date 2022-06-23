<template>
    <div class="portfolio" id="portfolio">
        <!-- In Spanish -->
        <h3 class="p_title" v-if="this.lang === 'Es'">¡Echa un vistazo a algunos de mis trabajos!</h3>

        <!-- In English -->
        <h3 class="p_title" v-if="this.lang === 'En'">Take a look at some of my work!</h3>


        <div class="computers">

            <div class="group">
                <h4 class="comp_title">Instagram</h4>

                <a class="instalink" href="https://www.instagram.com/ferrezcru_yeski/">
                    <div class="md-macbook-pro">
                        <div class="md-lid">
                            <div class="md-camera"></div>

                            <div class="md-screen">
                                <img class="screenshot" src="../assests/ferinsta.png"
                                    alt="Screenshot of instagram profile" />
                            </div>

                        </div>
                        <div class="md-base"></div>
                    </div>
                </a>
            </div>

            <div class="group">
                <h4 class="comp_title">Youtube</h4>

                <a class="facelink" href="https://www.youtube.com/channel/UCZIcfGDX_cA7Z0a7pM5o5HA/featured">
                    <div class="md-macbook-pro">
                        <div class="md-lid">
                            <div class="md-camera"></div>

                            <div class="md-screen">
                                <img class="screenshot" src="../assests/feryoutube.png"
                                    alt="Screenshot of Youtube channel" />
                            </div>

                        </div>
                        <div class="md-base"></div>
                    </div>
                </a>
            </div>

            <div class="group">
                <h4 class="comp_title">Facebook</h4>

                <a class="facelink" href="https://www.facebook.com/profile.php?id=100035027718099">
                    <div class="md-macbook-pro">
                        <div class="md-lid">
                            <div class="md-camera"></div>

                            <div class="md-screen">
                                <img class="screenshot" src="../assests/ferfacebook.png"
                                    alt="Screenshot of Facebook profile" />
                            </div>

                        </div>
                        <div class="md-base"></div>
                    </div>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['lang']
}
</script>

<style>
.portfolio {
    min-height: 90vh;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    z-index: 0;
}

.p_title {
    font-style: italic;
    font-weight: 800;
}

.computers {
    width: 100%;
    height: auto;
    display: flex;
    justify-content: space-evenly;
    align-items: center;
}

.comp_title {
    font-weight: 500;
}

.group {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.md-macbook-pro {
    width: 55.3125em;
    /* height: 31.875em; */
    font-size: 0.4em;
}

.md-macbook-pro .md-lid {
    width: 45em;
    height: 30.625em;
    margin: 0 auto;
    position: relative;
    border-radius: 1.875em;
    border: solid 0.1875em #cdced1;
    background: #131313;
}

.md-macbook-pro .md-camera {
    width: 0.375em;
    height: 0.375em;
    margin: 0 auto;
    position: relative;
    top: 1.0625em;
    background: #000;
    border-radius: 100%;
    box-shadow: inset 0 -1px 0 rgba(255, 255, 255, 0.25);
}

.md-macbook-pro .md-camera:after {
    content: "";
    display: block;
    width: 0.125em;
    height: 0.125em;
    position: absolute;
    left: 0.125em;
    top: 0.0625em;
    background: #353542;
    border-radius: 100%;
}

.md-macbook-pro .md-screen {
    width: 42.25em;
    height: 26.375em;
    margin: 0 auto;
    position: relative;
    top: 2.0625em;
    background: #1d1d1d;
    overflow: hidden;
}

.md-macbook-pro .md-screen img {
    width: 100%;
}

.md-macbook-pro .md-base {
    width: 100%;
    height: 0.9375em;
    position: relative;
    top: -0.75em;
    background: #c6c7ca;
}

.md-macbook-pro .md-base:after {
    content: "";
    display: block;
    width: 100%;
    height: 0.5em;
    margin: 0 auto;
    position: relative;
    bottom: -0.1875em;
    background: #b9babe;
    border-radius: 0 0 1.25em 1.25em;
}

.md-macbook-pro .md-base:before {
    content: "";
    display: block;
    width: 7.6875em;
    height: 0.625em;
    margin: 0 auto;
    position: relative;
    background: #a6a8ad;
    border-radius: 0 0 0.625em 0.625em;
}

.md-macbook-pro.md-glare .md-lid:after {
    content: "";
    display: block;
    width: 50%;
    height: 100%;
    position: absolute;
    top: 0;
    right: 0;
    border-radius: 0 1.25em 0 0;
    background: -webkit-linear-gradient(37deg, rgba(255, 255, 255, 0) 50%, rgba(247, 248, 240, 0.025) 50%, rgba(250, 245, 252, 0.08));
    background: -moz-linear-gradient(37deg, rgba(255, 255, 255, 0) 50%, rgba(247, 248, 240, 0.025) 50%, rgba(250, 245, 252, 0.08));
    background: -o-linear-gradient(37deg, rgba(255, 255, 255, 0) 50%, rgba(247, 248, 240, 0.025) 50%, rgba(250, 245, 252, 0.08));
    background: linear-gradient(53deg, rgba(255, 255, 255, 0) 50%, rgba(247, 248, 240, 0.025) 50%, rgba(250, 245, 252, 0.08));
}

.screenshot {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: top center;
    transition: all 5s ease-in-out;
}

.screenshot:hover {
    object-position: bottom center;
}

@media (max-width:992px) {
    .portfolio {
        margin: 3rem 0;
        justify-content: space-evenly;
        align-items: center;
    }

    .p_title {
        margin-top: 5rem;
    }

    .computers {
        flex-direction: column;
    }
}
</style>