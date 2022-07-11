<template>
  <div class="container">
    <div class="box-shodow d-flex flex-column">

      <div class="d-flex justify-content-between align-items-center">
        <img src="/image/archive.png">
        <div>
          <CircleProgress
              :percent="percent"
              :show-percent="true"
              :viewport="false"
              :border-width="10"
              :border-bg-width="10"
          />
        </div>
      </div>
      <span class="text-black-50">Pending sign offs</span>
      <div class="align-items-center">
      <p><span class="fw-bold fs-2">63 -  </span>   <span class="text-black-50 fs-4">17 </span></p>
      </div>
      <span class="text-black-50">Signed off in this week 221</span>
    </div>
  </div>
</template>

<script>
import "vue3-circle-progress/dist/circle-progress.css";
import CircleProgress from "vue3-circle-progress";
export default {
  components: {CircleProgress},
  data: () => ({
    percent:25,
  }),
  methods: {
      loop(){
        setInterval(()=>{
         if (this.percent === 25 ){
           this.percent = 1
         }
         else if(this.percent === 1){
           this.percent =25
         }

        },2500)
      }




  },
  mounted() {
    // this.loop()
    }
}


</script>


<style lang="scss">
body {
  //background: cadetblue;
}

.box-shodow {
  padding: 25px;
  display: flex;
  justify-content: center;
  margin: 0 auto;
  position: relative;
  top: 18rem;
  width: 28%;
  height: 20vh;
  border-radius: 32px;
  box-shadow: rgb(156 2 246) 0px -23px 1px 0px, rgb(120 0 250) 0px -51px 1px 0px, #00000059 0px 6px 7px 2px;
}

img {
  max-width: 41px;
  height: 45px;
}

.vue3-circular-progressbar {
  width: 55px !important;
  height: auto !important;
}
.current-counter{
  &::after{
    content: '%';
  }
  &::before{
    content: '+';
  }
}
</style>






