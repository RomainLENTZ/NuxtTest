<template>
    <h2>Test de la ligne</h2>
    <div class="line-wrapper">
        <svg version="1.1" id="svg" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
                viewBox="0 0 210 297" style="enable-background:new 0 0 210 297;" fill="none" stroke="#000000" stroke-width="1" stroke-miterlimit="10" xml:space="preserve">
            <path class="st0 line" d="M51.5,32.6c34.9-12.3,48.4-7.4,54.4-1.4c19.4,19-21.1,63.9,0,102.2c15.6,28.4,50.1,26,62,62
                c1.9,5.8,6.3,19.3,0,26.3c-12.2,13.6-49.4-13-65.5,0c-7.4,6-10.8,20.9,0,56.5"/>
        </svg>
    </div>
</template>

<script setup>
    import { gsap } from "gsap";
    import { ScrollTrigger } from "gsap/ScrollTrigger"
    
    onMounted(() => {
        gsap.registerPlugin(ScrollTrigger)

        let lineWrapper = document.querySelector(".line-wrapper");
        console.log(svg)
        let line = document.querySelector(".line");
        gsap.to(
        line, {
            
            ease: "power3.out",
            strokeDashoffset: 0,
            duration: 1,
            scrollTrigger: {
                trigger: lineWrapper,
                markers: true,
                scrub: 1,
                start: "top top",
                end: "bottom 70%"
            }

        }
        )
    })

</script>

<style lang="scss">
    body {
        margin:0;
        width: 100%;
        height: 3000px;
        background:white;
    }

    .line-wrapper{
        height: 246vh;
        position: relative;
    }

    svg{
        position:absolute;
        width:55%;
        top:15vh;
        overflow:visible;
        

        path {
            stroke-dasharray: 413;
            stroke-dashoffset: 413;
        }
    }
</style>