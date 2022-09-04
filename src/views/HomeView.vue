<template>
  <div class="home container">
    <div class="text ">
      <h1 v-if="!this.done">Freedom is nothing but a chance to be better</h1>
    <p   v-if="!this.done" class="mt-3">لإن الانتظار قاتل ولأنني علي يقين أن كل ما هُو أتٍ فهو قريب، فلا يسعُني سوي الاستيقاظ في كل يوم لأري أنني اقتربت يومًا من إنتهاء تلك الفترة أو كما   "أسمعُهم يقولون "نِلت حريتي
      
    </p>
     <h1 v-if="this.done" class="freedom"> نلنا الحرية اخيرا 🎆 🥰</h1>
    </div>

    <div v-if="!this.done" class="timer d-flex justify-content-center">
      <div class="days">
        <h1>{{this.displaydays}}:</h1>
        <p>Days</p>
      </div>
      <div class="hours">
        <h1>{{this.displayHours}}:</h1>
        <p>Hours</p>
      </div>
      <div class="minutes">
        <h1>{{this.displaymints}}:</h1>
        <p>Minutes</p>
      </div>
      <div class="seconds">
        <h1>{{this.displaysecends}}</h1>
        <p>Seconds</p>
      </div>
    </div>
  
  </div>
  <div class="footer container">

      <h1> Created By <a href="https://twitter.com/o_abdullnasser">Omar AbdullNasser</a> </h1>
    </div>
</template>

<script>




export default {
  name: 'HomeView',
  data() {
   return {
    displaysecends:0,
    displaymints:0,
    displayHours:0,
    displaydays:0,
    done:false,

   }
 },
 computed:{
    _secands:()=>1000,
    _mints(){
      return this._secands *60
    },
    
    _hours(){
      return this._mints *60
    },
    
    _days(){
      return this._hours *24
    },
 },
 methods:{

  ShowRemaining(){
    const timer = setInterval(()=>{
    const  now= new Date();
    const end=new Date(2023,6,1);
    const distance = end.getTime() - now.getTime();
    if( distance < 0){
      this.done();
      clearInterval(timer);
      return
    }

   
    const days = Math.floor(distance /this._days);
    const hours = Math.floor((distance % this._days)/ this._hours);
    const minutes = Math.floor((distance % this._hours)/ this._mints);
    const secands = Math.floor((distance % this._mints)/ this._secands);

    this.displaysecends= secands < 10 ? '0'+ secands: secands; 
    this.displaymints= minutes < 10 ? '0'+ minutes: minutes;
    this.displayHours= hours < 10 ? '0'+ hours : hours;
    this.displaydays= days < 10 ? '0'+ days: days;
    },1000);
  },
done(){
  this.done=true;
}

 },
 mounted(){ 
  this.ShowRemaining();
 },
}
</script>

<style lang="scss">
.text{
  color:#fff;
  text-align: center;
  h1{
    font-weight: bolder;
  }
  p{
    font-size: 30px;
  }
  .freedom{
    font-size: 100px;
  }
}
.timer{
  text-align: center;
  color:#fff;


  h1{
    font-size: 60px ;
   } 
   p{
    font-size: 30px;
   }

  .days{
    p{
      margin-right: 69px;
    }
  }
  .hours{
    p{
      margin-right: 69px;
    }
  }
  .minutes{
    p{
      margin-right: 30px;
    }
  }
 


}


.footer{
  margin-top: 5rem;
  h1{
    font-size: 20px ;
    color:#d78d5e
  }
  a{
    color:#fff;
    &:hover{
      color:rgba($color: #fff, $alpha: .5);
    }
  }
}

@media screen and  (max-width:425px){
   .timer{
    h1{
    font-size: 36px ;
   } 
    p{
    font-size: 10px;
   }
   .days{
    p{
      margin-right: 0;
    }
  }
  .hours{
    p{
      margin-right: 0;
    }
  }
  .minutes{
    p{
      margin-right: 0 ;
    }
  }

   } 
   .footer{
      margin-top: 1rem;
      h1{
        font-size: 15px ;
      }
      a{
        color:#fff;
        &:hover{
          color:rgba($color: #fff, $alpha: .5);
        }
      }
    }

    .text{
      p{
        font-size: 15px;
      }
    }
 }

</style>
