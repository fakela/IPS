<template>
   <div class="expect">
                <div class="l-wrapper">
                    <div class="flex-grid flex-grid--centered">
                        <div class="col col--wide">
                            <h1 class="expect__title">
                                    Ten Best Photo Apps for Incredible iphone Photography (2020 Edition)
                            </h1>
                            <div class="border"></div>
                            <div class="col col--super-wide">
                                <p class="text-p">
                                    How do you caoture more interesting travel photos with your iphone?How do you avoid taking the same cliche vacation picture that everyone else takes? i recently interviews Steffen Geldner - talented iphone photographer with a passion for travel. In this article Steffen reveals 7 tips for shooting beautiful travel photos that will preserve the amazing memory of your trip. Read on to discover how better travel photos with your iphone!
                                </p>
                                <br>
                                <img class="img-fluid reason__img img-fluid--stick-to-right  lazyload-img" src="/images/travel-photos.png">

                                <h2 class="blog-one">1. Reasearch Your Destination To Find The Best Photo Opportunities</h2>
                                <p>Befor the trip i recommend researching the destination to find the most innteresting photo opportunities</p>
                                <p> i always reasearch the location i'm travelling to. I do this extensively and obessively!</p>
                                <p>It's up to you to how much research you do. But you should spend a good time looking up some great places to take pictures.</p>
                                <p>So, what kind of research can you do?</p>
                                <p>First, you could search for photos that other people have taken at the locations were planning to visit.</p>
                                <p>Search on instagram and Google to get an idea of kinds of photos people take there.
                                </p>
                                <h2 class="blog-two">2. Capture Your Journey To The Complete Story Of Your Travels</h2>
                                <p>Travel Photography isn't just about Photographing the destination</p>
                                <p>For a more complete photographic story, capture your journey to and fro from the locatio your visiting</p>
                                <p>If your travelling by plae, try to get a window seat where you have view of wing or propeller.</p>
                                <p>And of course ,you could capture a beautiful aerial view of clouds, mountains, or city lights as your flying above.</p>
                                <p>Your journey will often involve several different types of transport. And they all offer great photo opportunities.</p>
                                <p> Whether your're travelling by car, taxi, bus, train, boat, or plane try to capture some interesting photos.</p>
                            </div>

                        </div>
                        <div class="col">
                            <div class="col__wrapper">
                                <div class="submition">
                                    <button  @click="on()" class="submition__button">Send Me The Tips</button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="submiton-popup" id="overlay">
                        <div class="submiton-popup__content" >
                            <button type="button" class="pop__close-btn close"  @click="off()">
                                <span aria-hidden="true">×</span>
                            </button>
                            <div class="pop__inner-block">
                                <p class="pop__slider-title">Step 1 of 2</p>
                                <div class="pop__slider-outer">
                                    <div class="pop__slider-inner"></div>
                                </div>
                                <h3 class="pop__title">Enter Your Email To Get <span class="green-text">FREE</span>  Iphone Photography Email Tips:</h3>
                                <form id="pop__form" class="pop__form" @submit.prevent="send()">
                                    <div class="form-group pop__input-block">
                                        <input type="email"
                                         class="form-control pop__field"
                                         id="pop__email"
                                         name="email"
                                         placeholder="Please enter your email here"
                                         v-model="email"
                                         required
                                         />
                                        <div
                                          class="msg"
                                            v-if="errorEmail != null"
                                           style="color:red;"
                                        >
                                          {{ errorEmail }}
                                          </div>
                                          <div
                                           class="msg"
                                            v-if="succsessMsg != null"
                                            style="color:green;"
                                          >
                                            {{ succsessMsg }}
                                            </div>
                                    </div>

                                    <button type="submit" class="btn btn-primary pop__submit">Send Me Tips</button>
                                </form>
                            </div>
                        </div>
                    </div>
                </div>
</template>

<script>
export default {
    data() {
        return {
            succsessMsg: null,
            errorEmail: null,
            email: null,
            reg: /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/
        };
    },
    mounted() {
        console.log("Component mounted.");
    },
    methods: {
        on() {
            document.getElementById("overlay").style.display = "block";
        },
        off() {
            document.getElementById("overlay").style.display = "none";
        },
        send() {
            if (this.email == null || this.email == "") {
                this.errorEmail = "Please Enter Email";
                return;
            } else if (!this.reg.test(this.email)) {
                this.errorEmail = "Please Enter Correct Email";
                return;
            }

            this.succsessMsg = "E-Mail Registered";
            return;
        }
    }
};
</script>
