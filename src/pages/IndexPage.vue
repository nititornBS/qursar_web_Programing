<template>
  <q-page  padding>
    <div>{{ gpa }}</div>
    <!-- <h1>This is my first app</h1> -->
    <p>{{ name }}</p>
    <p>{{ age }}</p>
    <div>address : <span v-html="address"></span></div>
    <div><div v-for="(val,property,index) in info" :key="index">
      {{ item }}{{ val }} {{ property }}
    </div></div>
    <div>
      <q-btn color="primary" icon="check" label="increase" @click="age++" />
      <q-btn color="pink" icon="check" label="decrease" @click="age--" />
      <q-btn color="primary" icon="check" label="+10" @click="increamental(10)" />
    </div>
    <div>
      <q-input v-model="text" type="text" label="Type the input" @keyup.alt.enter = "clearText"/>
      <div>Text : {{ text }}</div>
    </div>
<q-img  
  :src="url"
  :ratio="16/9"
  spinner-color="primary"
  spinner-size="82px"
>
<div class=" absolute-top text-center">This is capybara </div></q-img>    
    <ul>
      <ol>{{ hobbird[0] }}</ol>
      <ol>{{ hobbird[1] }}</ol>
      <ol>{{ hobbird[2] }}</ol>
    </ul>
  <ul>
    <li>{{ info.height }}</li>
    <li>{{ info.sex }}</li>
    <li>{{ info.weight }}</li>
  </ul>
  <div>Status : {{ getstatus() }}</div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data(){
    return{
      name: "myName",
      age: 20,
      gpa:4,
      address:"<i>phuket</i>",
      hobbird:["Swim","Rinning", "Tennis"],
      info: {
        sex:"sot specific",
        weight: 111,
        height: 222.2
      },
      url:"https://www.rainforest-alliance.org/wp-content/uploads/2021/06/capybara-square-1.jpg.optimal.jpg",
      text:null,
      
    }
  },
  methods:{getstatus(){
    if (this.gpa>3) return this.addition(10)
    return "Fail" 
  },
  addition(param){
    return this.gpa + param
  },
  increamental(param){
    this.age+= param
  },
  clearText(){
this.text = ""
  }
}
})
</script>
