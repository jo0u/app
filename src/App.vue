<template>
   <div>
     
     
     <div
     v-for="obj in todos"
     v-bind:key="obj.id"
     class="todos-items"
     >
     
     <img 
        v-if="obj.imgScr"
        :src="obj.imgScr"
     
     >
 {{ obj.title }}
    
</div>
</div>
  <TheHeader
  v-show="showHeader"
  
  />

<div v-if="showName">
  Nome: {{ name }}<br>
  Sobrenome: {{ lastName }}
</div>




<div v-if="acessLevel == 'admin'">Admin</div>
<div  v-else-if="acessLevel == 'marketing'">Marketing</div>
<div  v-else>User</div>








  <img

  alt="Vue logo"
   src="./assets/logo.png"
   
   >
 
 
 <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader.vue';

export default {
  name: 'App',
  components: {
   HelloWorld,
    TheHeader
  },
data(){
  return{
    showHeader:true,
    name:'Jon',
    lastName:'Snow',
    showName: false,
    acessLevel: 'marketing',
  
 
    todos: [
  {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false,
    "imgScr": "https://via.placeholder.com/150",
  },
  {
    "userId": 1,
    "id": 2,
    "title": "quis ut nam facilis et officia qui",
    "completed": false,
    "imgScr": "https://via.placeholder.com/150"

  },
  {
    "userId": 1,
    "id": 3,
    "title": "fugiat veniam minus",
    "completed": false
  },
  {
    "userId": 1,
    "id": 4,
    "title": "et porro tempora",
    "completed": true
  },
  {
    "userId": 1,
    "id": 5,
    "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
    "completed": false
  }
]
    


  }
}
  
}
</script>

<style>
.todos-items{
  background-color: black;
  margin: 0 0 5px 0;
  padding: 3px 6px;
  color:#fff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px;
}
</style>
