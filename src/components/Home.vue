<template>
  <div class="">
    <the-header></the-header>
    <div class="container">
      <div class="box1">
       <div class="podcast">
         <iframe src="https://anchor.fm/ashutosh-anand-tiwari/embed/episodes/Tech-Ki-Baat--Episode-02--Web-Frameworks-e13r0pf" height="102px" width="400px" frameborder="0" scrolling="no"></iframe>
       </div>
        <div  class="box1-content">
          <div class="counter-container">
            <div class="text">
               <p>Daily @9pm to 10pm</p>
            </div>
            <div class="timer">
               <!-- <the-timer></the-timer>  -->
            </div>
          </div>
         
          <h2 id="company-name">Ashtech Presents..</h2>
          <h1 id="program-name">Tech ki Baat in Desi Andaaz</h1>
          <p id="program-slogan">A Open Mic for Computer Engineers</p>
          <p  id="program-lang"> in हिंदी | ENGLISH  Daily @9pm </p>
          <h3 id="program-tag">Come and Join us & share your journey with us..</h3>
          <!-- <h2 id="program-timing">Daily @9pm On Twitter</h2> -->
          <button>
            <a href="https://twitter.com/YourVueJS"
              >Join Now <img src="../assets/smallmic.png" alt="" srcset=""
            /></a>
          </button>
  
          <button class="blue" :class="{red : showForm}" @click="openFeedbackForm">
            {{ showForm ? 'Close Form X' : 'Feedback'}} <img v-if="!showForm" src="../assets/feedback.png" alt="">
           
          </button>
        </div>
      </div>
      <div class="box2">
         <div v-if="showForm" class="form">
          <feedback></feedback>
        </div>
        <img v-else src="../assets/mic.jpg" alt="" srcset="" />
      </div>
    </div>
    <!-- <the-footer></the-footer> -->

   
  </div>
</template>

<script>
import TheHeader from "./Header.vue";
import Feedback from './Feedback.vue'
// import TheTimer from "./TheTimer.vue";

// import TheFooter from "./TheFooter.vue";
export default {
  components: {
    TheHeader,
    Feedback,
    // TheTimer,

 
    // TheFooter
  },
  data() {
    return {
      showForm:false
    }
  },
  
  methods: {
    openFeedbackForm(){
      this.showForm= !this.showForm
    },
    
  },
};
</script>


<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;

  height: 83vh;
}
.box1 {
  /* border: 1px solid red; */
  max-width: 400px;
  padding: 40px;
  /* background: linear-gradient(rgb(255, 255, 255), rgb(150, 252, 201)); */
}
#company-name {
  color: red;
  font-size: 20px;
  font-weight: bold;
}
#program-name {
  margin-top: 5px;
  color: rgb(0, 0, 0);
  text-shadow: 2px 4px 6px gray;
}
#program-slogan {
  margin-top: 5px;
  font-size: 0.8rem;
  color: blueviolet;
}

#program-tag {
  margin-top: 5px;
  color: orange;
  font-size: 1.4rem;
}
#program-timimg {
  font-weight: bolder;
}
#program-lang {
font-size: 1.8rem;
color: black;
font-weight: bolder;
}

.box2 {
  margin-top: 5px;
  /* border: 1px solid red; */
  max-width: 400px;
}
.box2 img {
  width: 360px;
}
button {
  background: yellow;
  font-size: 2rem;
  margin-top: 30px;
  border: none;
  outline: none;
  box-shadow: 2px 4px 6px gray;
  padding: 10px 20px;
  margin: 10px;
}
button a {
  text-decoration: none;
}
.blue{
   background: rgb(25, 64, 235);
  color: rgb(250, 250, 250);
  cursor: pointer;
}
.red{
  background: tomato;
  color: blanchedalmond;
  cursor: pointer;
}

@media screen and (min-width: 900px) {
  .box1,
  .box2 {
    max-width: 900px;
  }
  .box1 {
    width: 700px;
  }
  .box2 img {
    width: 550px;
  }
  #company-name {
    margin-top: 50px;
    font-size: 20px;
  }
  #program-name {
    font-size: 4rem;
  }
  #program-slogan {
    margin-top: 55px;
    font-size: 2rem;
    margin-bottom: 50px;
  }
  #program-tag {
    margin-top: 45px;
    font-size: 2rem;
  }
  #program-timimg {
    font-weight: bolder;
    font-size: 1.5rem;
  }
}

.counter-container{
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(#ee9ca7 ,#ffdde1);
  /* border: 1px solid black; */
  box-shadow: 2px 4px 6px gray ;
  border-radius: 20px;
  animation: animateTimer 3s linear alternate infinite;
}
.timer{
  padding: 20px;
  font-size: 1.4rem;
}
.text{
  font-size: 1.8rem;
  font-weight: bolder;
}

@keyframes animateTimer{
  to{
    transform: scale(1.1);
  }
  from{
    transform: scale(.9);
  }

}


  @media screen and (max-width:900px) {
      .counter-container{
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(#ee9ca7 ,#ffdde1);
  /* border: 1px solid black; */
  box-shadow: 2px 4px 6px gray ;
  border-radius: 10px;
  animation: animateTimer 3s linear alternate infinite;
  margin-bottom: 20px;
}
.timer{
  padding: 10px;
  font-size: 1rem;
}
.text{
   padding: 10px;
  font-size: 1.2rem;
}

  }
.podcast{
  background: rgb(239, 248, 245);
  justify-content: center;
  display: flex;
  box-shadow: 4px 6px 5px gray;
  margin-bottom: 10px;
}
 
</style>
