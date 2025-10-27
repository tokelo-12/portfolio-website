<template>
    
    <div class="gradient-bg">

        <div class="text-container">
            <h3 class="header-name">Tokelo Maloi</h3>
            <h4>Software Developer</h4>
            
            <div class="about-me-btn"><p>Creating amazing experiences one line of code at a time</p></div>

            <!-- <h4>Socials :</h4> -->

            <div class="img-container">
                <div class="socials">
                    <h6>Github</h6>
                    <a href="https://github.com/tokelo-12"><img src="../assets/github-sign.png" alt="github-logo" srcset=""></a>
                </div>
                <div class="socials">
                    <h6>LinkedIn</h6>
                    <a href="https://www.linkedin.com/in/tokelo-maloi-490b84266/"><img src="../assets/linkedin.png" alt="linkedin-logo" srcset=""></a>
                </div>
            </div>

            <h4>Skills :</h4>

            <div class="skills-section">
                <img src="../assets/Go-Logo_Aqua.png" alt="">
                <img src="../assets/Kotlin Full Color Logo Mark RGB.png" alt="">
                <img src="../assets/android-head_3D.png" alt="">
                <img src="../assets/gcloud.png" alt="">
                <img src="../assets/TS.png" alt="">
                <img src="../assets/logo.svg" alt="">
                <img src="../assets/sass.png" alt="">
                <img src="../assets/html-5.png" alt="">
                <img class="burn" src="../assets/k8s.png" alt="">
            </div>

           <a class="projects" href="https://github.com/tokelo-12"><p>Projects</p></a>

            <!-- <div class="tech-stack">
                <h4>Built With :</h4>

                <div class="stack-logos">
                    <img src="../assets/TS.png" alt="">
                    <img src="../assets/logo.svg" alt="">
                </div>
            </div> -->
        </div>    
    <svg xmlns="http://www.w3.org/2000/svg" version="1.1">
        <defs>
            <filter id="goo">
                <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="goo" />
                <feColorMatrix in="goo" type="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 18 -8" result="goo" />
                <feBlend in="SourceGraphic" in2="goo" />
            </filter>
        </defs>
    </svg>
    
    <div class="gradients-container">
            <div class="g1"></div>
            <div class="g2"></div>
            <div class="g3"></div>
            <div class="g4"></div>
            <div class="g5"></div>
            <div class="interactive" ref="interBubble"></div>
        </div>

    </div>
</template>

<script setup lang="ts">
    import{ref, onMounted, onUnmounted} from 'vue';

    const interBubble = ref()!;
    let cursorX : number = 0
    let cursorY : number = 0
    let targetX : number = 0
    let targetY : number = 0
        
        
        function move():void{
        cursorX += (targetX  - cursorX)/20;
        cursorY += (targetY - cursorY)/20;

        interBubble.value.style.transform = `translate(${Math.round(cursorX)}px , ${Math.round(cursorY)}px )` ;
        requestAnimationFrame(move)
    }

    onMounted(()=>{
        
        window.addEventListener('mousemove',(event) =>{
            targetX = event.clientX
            targetY = event.clientY
        });

        move();
    });


    onUnmounted(()=>{
        window.removeEventListener('mousemove', move);
    })
    

    
</script>

<style scoped lang="scss">
 @import '../assets/Bubbles.scss'
</style>