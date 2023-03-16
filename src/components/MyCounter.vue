<template>
  <div class="my-counter">
    <h1>My Counter app</h1>
  </div>
    <div class="counter">
      <div class="counter__value">{{ counter }}</div>
      <div class="counter__controls">
        <button class="counter__button" @click="increment">+</button>
        <input class="counter__input" type="number" v-model="counter" @input="updateCounter" />
        <button class="counter__button" @click="decrement">-</button>
      </div>
      <div class="reset-btn">
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
  body{
    background-image: linear-gradient(43deg, #4158D0 0%, #C850C0 50%, #FFCC70 100%);
 ;
  }
  .counter {
    transition: 600ms;
   
    /* border:1px solid red ; */
    border-radius: 12px;
    display: grid;
    grid-template-columns: 2fr, 2fr;
    justify-content: center;
    align-items: center;
    font-family: Arial, sans-serif;
  }
  .reset-btn{
    display: block;
    margin: 10px auto;
    background-color: rgb(216, 216, 231);
    border-radius: 4px;
    /* box-shadow: inset .2px .3px 2px 1px; */
  
  }
  .my-counter{
    display: block;
    align-items: center;
    justify-content: center;
    text-align: center;
    margin: 12px auto;
    color: #ffff;
    font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
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
    background-color: #ffff;
  }
  
  .counter__controls {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    justify-content: space-between;
    align-items: center;
    justify-content: center;
    width: 250px;
    margin: 10px auto;
    position: relative;
    left: 16px;
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
    margin: 10px auto;
    text-align: center;
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
    color: rgb(119, 105, 119);
    background-color: transparent;
    border: none;
    cursor: pointer;
    display: grid;
    ;
  }
  
  .counter__reset-button:hover {
    color: #4d4d4d;
  }
  @media (min-width: 550px){
    .counter{
      background-color:rgb(104, 73, 104) ;
      transition: 700ms;
      width: 650px;
      display: grid;
      align-items: center;
      justify-content: center;
      margin: 12px auto;

    }
  }
  </style>
  