<template>
  <div class="hello-container">
    <h1>Hello, World!</h1>
    <p>Welcome to Ayo's first Vue.js app 🎉</p>
    <button @click="showMessage = !showMessage">
      {{ showMessage ? 'Hide' : 'Show' }} Message
    </button>
    <transition name="fade">
      <div v-if="showMessage" class="message">
        Vue CLI is pretty cool! 
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      showMessage: false
    }
  }
}
</script>

<style scoped>
.hello-container {
  max-width: 500px;
  margin: 50px auto;
  padding: 30px;
  border-radius: 15px;
  background-color: #f3f4f6;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  text-align: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  color: #42b983;
  font-size: 2.5rem;
  margin-bottom: 10px;
}

p {
  font-size: 1.1rem;
  color: #333;
  margin-bottom: 20px;
}

button {
  background-color: #42b983;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 1rem;
  border-radius: 10px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #36966e;
}

.message {
  margin-top: 20px;
  font-weight: bold;
  color: #444;
  font-size: 1.1rem;
}

/* Fade animation */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
