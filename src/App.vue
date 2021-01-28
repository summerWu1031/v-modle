<template>
  <div id="app">
    <input placeholder="edit me" v-model="message">
    <p>I'm {{message}}</p>
    <button @click="message='sum'">set message to sum</button>
    <hr>
    <div>
      {{x}}
      <textarea v-model="x" placeholder="edit me"></textarea>
    </div>
    <hr>
    爱好：{{checkbox}}
    <label >
      <input name="hobby" type="checkbox" v-model="checkbox" :value="1">
      <span>rap</span>
    </label>
     <label >
      <input name="hobby" type="checkbox" v-model="checkbox" :value="2">
      <span>sing</span>
    </label>
     <label >
      <input name="hobby" type="checkbox" v-model="checkbox" value="3">
      <span>dance</span>
    </label>
    <hr>
    兴趣：{{select}}
    <select v-model="select" >
      <option value="">--</option>
      <option :value="1">rap</option>
      <option :value="2">sing</option>
      <option :value="3">dance</option>
    </select>
    兴趣：{{select}}
      <select v-model="select" >
      <option value="">--</option>
      <option v-for="item in array" :value="item.value" :key="item.value">{{item.text}}</option>
    </select>
    <hr>
    {{user}}
    <form @submit.prevent="onSubmit" >
      <label >
        <span>username:</span>
        <!-- <input type="text" :value="user.name" @input="user.name=$event.target.value" > -->
        <input type="text" v-model.lazy="user.name" >
      </label>
      <label >
        <span>password:</span>
        <input type="password" v-model.trim="user.password" >
      </label>
      <button type="submit">submit</button>
      <hr>
      <myInput v-model="user.name"/>
    </form>
  </div>
</template>

<script>
import myInput from './myinput.vue'
export default {
  name: 'App',
  data(){
    return{
      message:'user',
      x:'textarea',
      checkbox:[],
      select:[],
      array:[
        {text:'rap',value:1},
        {text:'sing',value:2},
        {text:'dance',value:3}
        ],
      user:{
        name:'',
        password:''
      }
    }
  },
  methods:{
    onSubmit(){
      console.log(this.user);
    }
  },
  components:{myInput}
}
</script>

