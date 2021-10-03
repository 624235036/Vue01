<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <br/>
    <span> {{ message1 }} </span> <br/>
    <span v-text="message2"></span>
    <hr/>
    <span> {{ counter}} </span> <br/>
    <button v-on:click="counter=counter+1">+</button>
    <button v-on:click="minus">-</button>
    <hr/>

    <span> {{ message3 }} </span> <br/>
    <input type="text" v-model="message3"/>
    <select v-model="message3">
      <option value="choice01">Hello 1 !!</option>
      <option value="choice02">Hello 2 !!</option>
      <option value="choice03">Hello 3 !!</option>
    </select><br/><br/>
    <textarea v-model="message3"></textarea>
    <hr/>
    <input v-bind:type="inputtype" /><br/>

    <img v-bind:src="require(`@/assets/images/` +imagename)">
      <select v-model="imagename"><br/>
      <option value="hh.jpg"> Image 1</option>
      <option value="jj.jpg"> Image 2</option>
    </select><br/><br/>
    <hr/>

    <h1 v-show="isGreeting">  Hello !!! </h1>

    <hr/>
    {{htmlText}}<br/>
    <span v-html="htmlText"></span>
    <hr/>

    <div v-bind:key="emp.id" v-for="emp in employees">
      <b>Id</b>: {{emp.id}},<br/>
      <b>Name</b>: <span v-bind:class="(emp.Salary>90000) ? 'high' : (emp.Salary>=30000) ? 'medium' : 'low'">{{emp.name}}</span>,<br/>
      <b>Salary</b>: {{emp.Salary}}
      <span v-if="emp.Salary>90000">***</span>
      <span v-else-if="emp.Salary>=30000">**</span>
      <span v-else>*</span>
      
      <br/><br/><br/>
    </div>
    <hr/>

    <div v-bind:key="std.studentId" v-for="std in students">
      <b>studentId</b>: {{std.studentId}},<br/>
      <b>firstName</b>: {{std.firstName}},<br/>
      <b>lastName</b>: {{std.lastName}}<br/>
      <b>score</b>: {{std.score}}<br/><br/>
    </div>


    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  data(){
    return {
      message1 : "Hello World!",
      message2 : "Hello Vinny",
      message3 : "Type here",
      inputtype : "redio",
      imagename : "hh.jpg",
      counter : 0,
      htmlText : "<b>HTML TEXT</b>&nbsp;",
      isGreeting : true,
      employees : [{"id":1,"name":"John","Salary":30000},{"id":2,"name":"Trump","Salary":10000},{"id":3,"name":"Peter","Salary":99000}],
      students : [{"studentId":624235036,"firstName":"kuasuwan","lastName":"kuji","score":50,},
      {"studentId":624235034,"firstName":"white","lastName":"fang","score":40,},
      {"studentId":624235033,"firstName":"kullapat","lastName":"sang","score":30,},
      {"studentId":624235035,"firstName":"cardi","lastName":"B","score":20,}]
    }
  },
  
  methods: {
    minus: function(){
      this.counter=this.counter-1
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.high{
  color: red;
}
.medium{
  color: blue;
}
.low{
  color: green;
}
</style>
