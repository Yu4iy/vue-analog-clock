<template>
  <div id="app">
    <main>
      <div class="clock">
        <div  class="center"></div>
        <div ref="hr" class="hr" :style="styleHr"></div>
        <div ref="min" class="min" :style="styleMin"></div>
        <div  class="sec"  :style="styleSec" ></div>
        <div class="number n1">1</div>
        <div class="number n2">2</div>
        <div class="number n3">3</div>
        <div class="number n4">4</div>
        <div class="number n5">5</div>
        <div class="number n6">6</div>
        <div class="number n7">7</div>
        <div class="number n8">8</div>
        <div class="number n9">9</div>
        <div class="number n10">10</div>
        <div class="number n11">11</div>
        <div class="number n12">12</div>
      </div>
    </main>
  </div>
</template>

<script>

import dayjs from 'dayjs'
export default {
  name: 'App',
  data(){
    return{
      activeColor: 'red',
     
      sec:0,
      min:0,
      hr:0,
    }
  },
  components: {
    
  },
  computed:{
    styleSec () {
        return { transform: 'rotate(' + this.sec + 'deg)'};
     },
    styleMin () {
        return { transform: 'rotate(' + this.min + 'deg)'};
     },
    styleHr () {
        return { transform: 'rotate(' + this.hr + 'deg)'};
     }        
  },
  created(){
    this.getDate();
  },

  methods:{
    getDate() {
      
    const self = this;          
     setInterval(function(){
        const today = dayjs();
            self.sec = today.format('ss')/60 * 360 ;
            self.min = today.format('mm')/60 * 360 ;
            self.hr = today.format('hh')/12 * 360 ;
            

      }, 1000);
    },

  }
}
</script>

<style lang="scss">
#app{
    background: rgb(106, 114, 128);
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;

}
  main{
    display: flex;
    justify-content: center;
    height: 100vh;
    align-items: center;
    transform: rotate(270deg);
    .clock{
      background: rgb(8, 123, 177);
      width: 400px;
      height: 400px;
      border-radius: 50%;
      position: relative;
    box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset, rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset, rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px, rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px, rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;

      .center{
        width: 10px;
        height: 10px;
        position: absolute;
        top: 50.5%;
        left: 49%;
        z-index: 6;
        transform: translate(-49%, -50.5%);
        border-radius: 81px;
        border: 2px solid rgba(4, 28, 44, 0.699);
        background: #ff0000;
        box-shadow: inset 9px 9px 18px #660000,
                    inset -9px -9px 18px #ff0000;

      }
      .hr{
        width: 90px;
        height: 10px;
        background: rgb(0, 0, 0);
        position: absolute;
        top: 49%;
        left: 49%;
        transform-origin: left;
        transform: translate(-0%, -50%);
        z-index: 4;
        border-radius:0 70%  70% 0;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;


      }
       .min{
        width: 130px;
        height: 10px;
        background: rgb(6, 5, 44);
        position: absolute;
        top: 49%;
        left: 49%;
        transform-origin: left;
        transform: translate(-0%, -50%);
        z-index: 4;
        border-radius:0 70%  70% 0;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;



      }
       .sec{
        width: 170px;
        height: 10px;
        background: rgb(7, 22, 44);
        position: absolute;
        top: 49%;
        left: 49%;
        transform-origin: left;
        transform: translate(-0%, -50%);
        z-index: 4;
        border-radius:0 70%  70% 0;
        box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;

      }
    }
  }

  .number{
    width: 100%;
    position: absolute;
    height: 100%;
    transform: rotate(90deg);
    text-align: center;
    font-size: 50px;
    z-index: 1;
    color: #fff;
    
      
    
  }
  .n1{
    transform: rotate(120deg);

  }
   .n2{
    transform: rotate(150deg);

  }
   .n3{
    transform: rotate(180deg);

  }
   .n4{
    transform: rotate(210deg);

  }
   .n5{
    transform: rotate(240deg);

  }
   .n6{
    transform: rotate(270deg);

  }
   .n7{
    transform: rotate(300deg);

  }
   .n8{
    transform: rotate(330deg);

  }
   .n9{
    transform: rotate(360deg);

  }
   .n10{
    transform: rotate(390deg);

  }
   .n11{
    transform: rotate(420deg);

  }
   .n12{
    transform: rotate(450deg);

  }          
</style>
