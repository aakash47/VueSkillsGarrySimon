<template>
  <div class="hello">
    <button v-on:click="addSkill">Submit</button>
    <form @submit.prevent="addSkille">
    <input type="text" placeholder="enter a skill" v-model="skill">
    <!-- <p class="alert" v-if="errors.has('skill')">{{errors.first('skill')}}></p> -->
    <input type="checkbox" id="checkbox" v-model="checked">
    </form>
    <ul>
       <transition-group name="alert-in" enter-active-class="animated  bounceInUp" leave-active-class="animated bounceOutDown">
        <li v-for="(data,index) in skills" :key="index" >
        {{data.skillname}}
        <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
      </li>
      </transition-group>
    </ul>
    <transition name="alert-in" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
      <p>Hello brother</p>
    </transition>
    <!-- <div v-bind:class="alertobject">
      
    </div> -->
    <!-- <h1>Hello Skills {{name}}</h1>
    {{ btnState ? 'the button is disabled' : 'the button is active' }} -->
        <!-- <div class="holder"> -->
          <!-- <ul> -->
            <!-- <li v-for="(data,index) in skills" :key="index">
              {{data}}
              {{index}}
              {{data.skill}}
            </li> -->
          <!-- </ul>
          <ul>
          <li v-for="(data,index) in student" :key="index" > -->
            <!-- temp={{data.fathername}} -->
              <!-- {{data.fathername}}<br>{{index}} -->
              <!-- <div v-if="student.length==2">
                <h1>Aakash solaki</h1>
              </div>
              <div v-else>
                <h1>vijay</h1>
              </div>
            </li>
          </ul>
        </div> -->

    <!-- <button v-on:click="changeName" v-bind:disabled="btnState">
      change name
    </button>    
    <h1>{{ 5>4 ? 'true' : 'false' }}</h1> -->
  
  <!-- <div v-bind:style="{backgroundColor:bgColor,width:bgWidth,height:bgHeight}">
  </div> -->

  </div>
</template>

<script>
export default {
  name: 'Skills',
  data (){ 
  return {
    skill:"",
    checked: false,
    // name:'coursera',
    // btnState:true,
    // alertobject:{
    //   alert:true,
    //   another_class:true
    //             },
    // temp:"",
    skills:[
      {"skillname":"Vue.js"},
      {"skillname":"frontend"},
    ],
    // student:[
    //   {
    //   "name":"aakash",
    //   "fathername":"hiranand",
    // },
    // {
    //   "name":"vijay",
    //   "fathername":"magharam",
    // }
    // ],
    // bgColor:'pink',
    // bgWidth:'100%',
    // bgHeight:'30px',

  }
},
methods: {
  addSkill(){
    this.skills.push({skillname: this.skill})
    // this.skills.reverse()
    this.skill=""
    
  },
  addSkille(){
    this.skills.push({skillname: this.skill})
    // this.skills.reverse()
    this.skill=""
    console.log(this.checked)
  },
  remove(id){
    this.skills.splice(id,1)
  }
  },
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css"; 
  .holder {
    background: #fff;
  }
  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }
  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }
  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
  }
  .alert {
    background: #fdf2ce;
    font-weight: bold;
    display: inline-block;
    padding: 5px;
    margin-top: -20px;
  }
  /* .alert-in-enter-active {
    animation: bounce-in .5s;
  }
  .alert-in-leave-active {
    animation: bounce-in .5s reverse;
  } */
/* @keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
} */
i {
  float:right;
  cursor:pointer;
}
/* .alert
{
  background-color: red;
  width:100%;
  height:30px;
}
.another_class{
  border:5px solid blue;
} */
</style>
