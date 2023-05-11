<template>
    <div class="title-wrapper">
        <h1 class="text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</h1>
        <h1 data-splitting="chars" class="text text-color">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</h1>
    </div>
</template>

<script setup>
    import { gsap } from "gsap";
    import { ScrollTrigger } from "gsap/ScrollTrigger"
    import "splitting/dist/splitting.css";
    import "splitting/dist/splitting-cells.css";
    import Splitting from "splitting";

    onMounted(() => {
        Splitting();
        let titleWrapper = document.querySelector(".title-wrapper");
        let chars = document.querySelectorAll('.char');

        gsap.registerPlugin(ScrollTrigger)
        
        gsap.to(
            chars, {
                ease: "power3.out",
                autoAlpha: 1,
                duration: 1,
                stagger: 0.05,
                scrollTrigger: {
                    trigger: titleWrapper,
                    markers: true,
                    scrub: 1,
                    start: "top 40%",
                    end: "bottom center"
                }
            }
        )
    })

</script>

<style lang="scss">
    
    .title-wrapper{
        position: relative;
    }

    .text{
        font-size: 15vh;
        font-family: sans-serif;
        color: rgb(37,37,37);
        
    }

    .text-color{
        color: red;
        position: absolute;
        top: 0;
        margin-top: 0;
                
        .char{
            opacity: 0;
        }
    }

    
</style>

