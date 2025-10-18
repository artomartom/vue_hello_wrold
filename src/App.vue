<template>
  <div id="app">
    <header>
      <h1>{{ title }}</h1>
    </header>
    <main>
      <div class="container">
        <p class="greeting">{{ greeting }}</p>
        <input 
          v-model="userName" 
          placeholder="What's your name?" 
          class="input-field"
        >
        <button @click="sayHello" class="btn">Say Hello</button>
        <p v-if="userName" class="personal-greeting">
          Nice to meet you, {{ userName }}! 🎉
        </p>
        
        <div class="counter">
          <button @click="decrement" class="btn btn-secondary">-</button>
          <span class="count">{{ count }}</span>
          <button @click="increment" class="btn btn-secondary">+</button>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      title: 'Vue Hello World App',
      greeting: 'Welcome to Vue.js!',
      userName: '',
      count: 0
    }
  },
  methods: {
    sayHello() {
      alert(`Hello, ${this.userName || 'stranger'}!`);
    },
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.greeting {
  font-size: 1.5em;
  color: #42b883;
  margin-bottom: 30px;
}

.input-field {
  padding: 10px;
  font-size: 16px;
  border: 2px solid #42b883;
  border-radius: 5px;
  margin: 10px;
  width: 200px;
}

.btn {
  background-color: #42b883;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  border-radius: 5px;
  cursor: pointer;
  margin: 5px;
}

.btn:hover {
  background-color: #369870;
}

.btn-secondary {
  background-color: #64748b;
}

.btn-secondary:hover {
  background-color: #475569;
}

.personal-greeting {
  font-size: 1.2em;
  color: #35495e;
  margin-top: 20px;
}

.counter {
  margin-top: 30px;
}

.count {
  font-size: 2em;
  margin: 0 20px;
  font-weight: bold;
}
</style>
