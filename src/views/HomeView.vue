<template>
    <div class="desktop-flex">
        <div class="home-section home-section-desktop">
            <div id="home-imgs">
                <img :src=currentImage alt="">
            </div>
            <nav id="nav">
                <i class="bi bi-list" @click="openMenu"></i>
                <div>
                    <ul class="nav-links" :class="{'hide': menuClose}">
                        <li class="nav-link">Home</li>
                        <li class="nav-link">About</li>
                        <li class="nav-link">Room</li>
                        <li class="nav-link">Contact Us</li>
                        <li class="nav-link">About Us</li>
                    </ul>
                </div>
                <h1 id="logo">room</h1>
            </nav>

            <div class="btns btns-deskop">
                <svg @click="prev" width="14" height="24" xmlns="http://www.w3.org/2000/svg">
                    <path d="M13 0L1 12l12 12" stroke="#FFF" fill="none" fill-rule="evenodd" />
                </svg>
                <svg @click="next" width="14" height="24" xmlns="http://www.w3.org/2000/svg">
                    <path d="M1 0l12 12L1 24" stroke="#FFF" fill="none" fill-rule="evenodd" />
                </svg>
            </div>
        </div>
        <div class="discover-section innovative-section-desktop">
            <section class="innovative">
                <h1 class="ptb">Discover innovative wasy to decorate</h1>
                <p class="discover-text text-opacity">We provide unmatched quality, comfort, and style for property owners
                    across the country. Our experts combine form and functino in bringing your vision to life. Create a room
                    in your own style with our collection and make your property a reflection of you and what you love.</p>

                <button class="btn-shop">SHOP NOW <svg width="40" height="12" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M34.05 0l5.481 5.527h.008v.008L40 6l-.461.465v.063l-.062-.001L34.049 12l-.662-.668 4.765-4.805H0v-1h38.206l-4.82-4.86L34.05 0z"
                            fill="#000" fill-rule="nonzero" />
                    </svg></button>
            </section>

        </div>
    </div>

    <div class="about-desktop">
        <div>
            <img src="../assets/images/image-about-dark.jpg" alt="">
        </div>

        <div class="discover-section">
            <h1 class="about-title">ABOUT OUR FURNITURE</h1>
            <p class="about-text text-opacity">Our multifunctional collection blends design and function to suit your
                individual taste. Make each room unique, or pick a cohesive theme that best express your interests and what
                inspires you. Find the furniture pieces you need, from traditional to contemporary styles or anything in
                between. Product specialists are available to help you create your dream space.</p>
        </div>

        <div>
            <img src="../assets/images/image-about-light.jpg" alt="">
        </div>

    </div>
</template>

<script>
import image1 from '../assets/images/desktop-image-hero-1.jpg'
import image2 from '../assets/images/desktop-image-hero-2.jpg'
import image3 from '../assets/images/desktop-image-hero-3.jpg'

export default {
    data() {
        return {
            slides: [image1, image2, image3],
            currentIndex: 1,
            menuClose: true
        }
    },
    computed: {
        currentImage() {
            return this.slides[this.currentIndex]
        }
    },
    methods: {
        next() {
            this.currentIndex = (this.currentIndex + 1) % this.slides.length
        },

        prev() {
            if (this.currentIndex > 0) {
                this.currentIndex--
            }
        },
        openMenu(){
            this.menuClose =! this.menuClose
        }
    }
}
</script>

<style scoped>
img {
    max-width: 100%;
    display: block;
}


/* Nav Styling */

.home-section {
    position: relative;
}

#home-imgs {
    width: 100%;
}

img {
    max-width: 100%;
    display: block;
    position: relative;
}

#nav {
    display: flex;
    align-items: center;
    padding: 2rem 1.5rem;
    color: #fff;
    position: absolute;
    z-index: 99;
    top: 0;
}

#logo {
    margin-inline: 5rem;
    font-weight: 600;
}

.nav-links {
    position: absolute;
    top: 3.5rem;
    left: 1.6rem;
    list-style: none;
}

.hide{
    display: none;
}

.nav-link{
    padding-block: .5rem;
}

.btns {
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 6rem;
    height: 3rem;
    background-color: var(--black);
    position: absolute;
    right: 0;
    bottom: 0;
}

/* Nav Styling End */

.discover-section {
    margin: 2rem;
}

.discover-text {
    color: var(--veryDarkGray);
    font-weight: 500;
    opacity: 0.6;
}

.btn-shop {
    margin-block: 2rem;
    border: none;
    background-color: transparent;
    letter-spacing: .5rem;
    font-weight: 600;
}

/* About section */

.about-title {
    font-size: .8rem;
    font-weight: 700;
    letter-spacing: .5rem;
    padding: 2rem 0 1.4rem 0;
}

/* Media Queries */

@media only screen and (width >=90rem) {

    #nav {
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        color: #fff;
        font-weight: 500;
        position: absolute;
        z-index: 99;
        top: 0;
        padding: 3rem 0 1rem 3rem;
    }

    #nav>i {
        display: none;
    }

    .nav-links {
        display: flex;
        list-style: none;
        position: inherit;
    }

    #logo {
        font-weight: 500;
        padding-right: 2rem;
    }

    .nav-link {
        padding-inline: 1rem;
    }

    .desktop-flex {
        display: flex;
    }

    .innovative-section-desktop {
        width: 30%;
    }

    .innovative {
        display: flex;
        flex-direction: column;
        justify-content: center;
        height: 100%;
    }

    .discover-section {
        width: 40%;
    }

    .btn-shop {
        align-self: baseline;
    }

    .btns {
        right: -10.4rem;
        width: 10.4rem;
        height: 4rem;
    }

    .about-desktop {
        display: flex;
    }
}
</style>