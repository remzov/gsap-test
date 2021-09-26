<template>
  <div class="container">

      <div class="section">
          <div ref="box" class="box"></div>
          <div  ref="test" class="test"></div>
      </div>
  </div>
 </template>

<script>
import { gsap } from 'gsap/dist/gsap'
import { ScrollTrigger } from 'gsap/dist/ScrollTrigger'

if (process.client) { gsap.registerPlugin(ScrollTrigger) }


export default {
    mounted() {
        var tl = gsap.timeline(
            {
                scrollTrigger: {
              		trigger: ".section",
              		start:"bottom bottom",
                }
            }
        )

        tl
            .to(this.$refs.box, {rotation: 27, x: 300, duration: 1})
            .to(this.$refs.test, {y: -300, duration: 1});
    }
}
</script>

<style lang="css" scoped>
.section {
    margin-top: 500px;
    margin-bottom: 300px;
    border: 1px solid green;
}


.box {
    margin-top: 500px;
    width: 100px;
    height: 100px;
    background-color: green;
}

.test {
    margin-top: 200px;
    width: 100px;
    height: 100px;
    background-color: yellow;

}
</style>
