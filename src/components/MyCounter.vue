<template>
    <div class="counter">
      <div class="counter__value">{{ counter }}</div>
      <div class="counter__controls">
        <button class="counter__button" @click="increment">+</button>
        <input class="counter__input" type="number" v-model="counter" @input="updateCounter" />
        <button class="counter__button" @click="decrement">-</button>
        <button class="counter__reset-button" @click="reset">Reset</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        counter: 0,
        min: 0,
        max: 100,
      };
    },
    methods: {
      increment() {
        if (this.counter < this.max) {
          this.counter++;
        }
      },
      decrement() {
        if (this.counter > this.min) {
          this.counter--;
        }
      },
      updateCounter() {
        if (this.counter < this.min) {
          this.counter = this.min;
        } else if (this.counter > this.max) {
          this.counter = this.max;
        }
      },
      reset() {
        this.counter = 0;
      },
    },
  };
  </script>
  
  <style>
  .counter {
    display: grid;
    grid-template-columns: 2fr, 2fr;
    justify-content: center;
    align-items: center;
    font-family: Arial, sans-serif;
  }
  
  .counter__value {
    border: 1px solid #ccc;
    padding: 15px;
    border-radius: 5px;
    display: grid;
    place-items: center;
    margin: 80px auto;
    font-size: 4rem;
    font-weight: bold;
    color: #4d4d4d;
    width: 200px;
  }
  
  .counter__controls {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    justify-content: space-between;
    align-items: center;
    justify-content: center;
    width: 250px;
    margin: 10px auto;
  }
  
  .counter__button {
    font-size: 2rem;
    color: white;
    background-color: #4d4d4d;
    border: none;
    border-radius: 50%;
    width: 50px;
    height: 50px;
    cursor: pointer;
  }
  
  .counter__button:hover {
    background-color: #6f6f6f;
  }
  
  .counter__input {
    font-size: 1.5rem;
    text-align: center;
    color: #4d4d4d;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 5px;
    width: 95px;
    margin: 5px;
  }
  
  .counter__reset-button {
    font-size: 1.5rem;
    color: #df1f1f;
    background-color: transparent;
    border: none;
    cursor: pointer;
    display: grid;
    ;
  }
  
  .counter__reset-button:hover {
    color: #4d4d4d;
  }
  </style>
  