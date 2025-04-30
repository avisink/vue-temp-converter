<template>
    <div class="converter-container">
      <div class="converter-card">
        <h2>Ayomide's Temperature Converter</h2>
        <div class="input-group">
          <label for="celsius">Celsius</label>
          <input
            id="celsius"
            type="number"
            v-model.number="celsius"
            @input="convertToFahrenheit"
            placeholder="Enter °C"
          />
        </div>
        <div class="input-group">
          <label for="fahrenheit">Fahrenheit</label>
          <input
            id="fahrenheit"
            type="number"
            v-model.number="fahrenheit"
            @input="convertToCelsius"
            placeholder="Enter °F"
          />
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'TempConverter',
    data() {
      return {
        celsius: 0,
        fahrenheit: 32,
        isUpdating: false
      }
    },
    methods: {
      convertToFahrenheit() {
        if (this.isUpdating) return;
        this.isUpdating = true;
        this.fahrenheit = (this.celsius * 9) / 5 + 32;
        this.isUpdating = false;
      },
      convertToCelsius() {
        if (this.isUpdating) return;
        this.isUpdating = true;
        this.celsius = ((this.fahrenheit - 32) * 5) / 9;
        this.isUpdating = false;
      }
    },
    mounted() {
      this.convertToFahrenheit();
    }
  }
  </script>
  
  <style scoped>
  .converter-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: linear-gradient(to right, #c9d6ff, #e2e2e2);
  }
  
  .converter-card {
    background: white;
    padding: 30px 40px;
    border-radius: 16px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    max-width: 400px;
    width: 100%;
    text-align: center;
  }
  
  h2 {
    color: #333;
    margin-bottom: 24px;
  }
  
  .input-group {
    margin-bottom: 20px;
    text-align: left;
  }
  
  label {
    display: block;
    font-weight: 600;
    margin-bottom: 8px;
    color: #444;
  }
  
  input {
    width: 100%;
    padding: 10px 12px;
    border: 1px solid #ccc;
    border-radius: 8px;
    font-size: 16px;
    transition: border 0.3s ease;
  }
  
  input:focus {
    outline: none;
    border-color: #42b983;
    box-shadow: 0 0 0 2px rgba(66, 185, 131, 0.2);
  }
  </style>
  