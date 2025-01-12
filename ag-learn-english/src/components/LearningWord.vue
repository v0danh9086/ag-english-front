<template>
  <div class="home">
    <h1>Welcome to Your English Learning Platform</h1>
    
    <div class="word-checker">
      <p>Type a word you want to learn and check it:</p>
      <input 
        type="text" 
        v-model="newWord" 
        placeholder="Enter a new word" 
        @keyup.enter="checkWord" 
      />
      <button @click="checkWord">Check Word</button>
    </div>
    
    <div v-if="result" class="result">
      <p>{{ result }}</p>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      newWord: "", // To store the user's input
      result: "" // To display the result after checking
    };
  },
  methods: {
    checkWord() {
      if (!this.newWord) {
        this.result = "Please enter a word to check.";
      } else {
        // Here you can add API integration to check the word or provide feedback.
        this.result = `The word "${this.newWord}" looks great! Keep learning!`;
        // Reset the input field after checking
        this.newWord = "";
      }
    }
  }
};
</script>

<style scoped>
.home {
  text-align: center;
  margin-top: 50px;
}

.word-checker {
  margin: 20px auto;
  max-width: 400px;
}

input {
  width: 80%;
  padding: 10px;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

button {
  padding: 10px 20px;
  background-color: #007BFF;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

.result {
  margin-top: 20px;
  font-size: 18px;
  color: green;
}
</style>
