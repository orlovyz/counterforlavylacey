<script>
export default {
  data() {
    return{
      words: [],
      newWord:''
    }
    
  },

  computed:{
    count() {
      return this.words.length;
    }
  },

  methods: {
    addWord() {
      if (this.newWord !== ""){
      this.words.push(this.newWord.slice());
      this.newWord='';
      }
      else {
        alert('Введи слово, дурик :)')
      }
      
      
    },
    removeWord() {
      this.words.pop();
      
    },
    removeArray(){
      this.words = [];
      
    },
    asshole(){
      console.log('жопа');
    }
  }
  
}
</script>
<template>
  <div>
    <p v-if="words.length ===0" @click="asshole">СПИСОК ПУСТ, УВЫ</p>
    <p v-else @click="asshole">СЧЕТЧИК ХЕРНИ: {{ count }}</p>
      
    
    <input type="text" v-model="newWord" placeholder="Введи слово, чорт!" @keyup.enter="addWord">
  <div>
<button @click.prevent="addWord">+</button>
<button @click="removeArray">remove array</button>
<button @click="removeWord">-</button>

</div>


  <li v-for="word in words" :key="word">
    {{ word }}
  </li>

</div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
