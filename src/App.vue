<template>
   <div>
     
    <div>
      Two-way data bindindg
    </div>

    <br><br>
<label for="">Nome</label>
<br>
    <input 
    v-model="nameModel"
    type="text"
    
    >
    <br>

    {{ nameModel }}
<br><br>
    <div>
      <label for="">Sports bet</label><br>
      <select v-model="sports">
        <option value="">Escolha</option>
        <option value="futebol">futebol</option>
        <option value="basket">basket</option>
        <option value="skate">skate</option>
        <option value="tenis">tenis</option>
      </select>
      <br>
      {{ sports }}
    </div>





    <div>
      <br><br><br>
      <label for="">Newsletter</label><br>
      <input 
       v-model="newsletter" type="radio" value="sim">sim
      <input 
        v-model="newsletter" type="radio" value="nao">nao
    </div>
<br>
{{ newsletter }}
<br><br><br><br>


<div>
      <br><br><br>
      <label for="">Contrato</label><br>
      <input 
       v-model="contratos" type="checkbox" value="sim">Aceita nosso contrato
     <br>
       {{ contratos }}
    </div>



    <div>
      <br><br><br>
      <label for="">Escolha a cor que você gosta</label><br>
      <input 
       v-model="colors" type="checkbox" value="azul">Azul

       <input 
       v-model="colors" type="checkbox" value="amarelo">Amarelo
     <br>
       {{ colors }}
    </div>








    <h1 :class="{'title':true, 'title-home': isHome}">
      Curso Vue 3

    </h1>


    <p :class="pClass">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus laborum ducimus quas, repudiandae veritatis officiis nostrum! Reprehenderit fuga aliquid, fugit suscipit dolor neque illo perspiciatis numquam expedita. Error, maiores corrupti.
    </p>
     


    <p :style="styleClass">
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. In totam, assumenda vel facilis consectetur rerum inventore facere animi voluptates cumque ducimus sunt corporis voluptatum numquam aspernatur sed! Veniam, quaerat dolores.
    </p>

     <div
     v-for="obj in todos"
     :key="obj.id"
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
    colors:[],
    contratos:false,
    nameModel:'jozi',
    newsletter:'',
    showHeader:true,
    name:'Jon',
    lastName:'Snow',
    showName: false,
    acessLevel: 'marketing',
    classVar: 'title',
    pClass: ['text','text-home'],
    isHome: false,
    styleClass: {color:'aqua', backgroundColor:'black', fontSize: '20px'},
    sports: 'futebol',



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
  }]
    


  }
}
  
}
</script>

<style>


.title{
  font-size: 20px ;
  color:blue;
}
.title-home{
  font-size: 40px;
  color:green;
}
.text{
  color:gray
}

.text-home{
  color: chartreuse;
}

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
