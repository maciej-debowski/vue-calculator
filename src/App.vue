<template>

  <div class="flex-box">
    <div class="calculator">
      <input type="text" placeholder="" v-model="value">
      <div class="keyboard">
        <button @click="value += '9'">9</button>
        <button @click="value += '8'">8</button>
        <button @click="value += '7'">7</button>
        <button @click="value += '/'">/</button>
        <button @click="value += '6'">6</button>
        <button @click="value += '5'">5</button>
        <button @click="value += '4'">4</button>
        <button @click="value += '-'">-</button>
        <button @click="value += '3'">3</button>
        <button @click="value += '2'">2</button>
        <button @click="value += '1'">1</button>
        <button @click="value += '+'">+</button>
        <button @click="calculate" class="equal">=</button>  
        <button @click="value = ''">C</button>
        <button @click="value += '*'">*</button>
      </div>
    </div>

    <footer>
      Design and Code by Maciej Dębowski. Created with Vue &amp; Love :)
    </footer>
  </div>

  
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    calculate() {
      this.value = eval(this.value)
    }
  }
}
</script>

<style>
  @import 'https://fonts.googleapis.com/css2?family=Roboto&display=swap';
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Roboto', sans-serif;
  }

  .flex-box {
    width: 100%;
    height: 100vh;
    background: #141629;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
  }

  .calculator {
    background: #eee;
    border-radius: 46px;
    padding: 20px;
    width: 425px;
    /*height: 550px;*/
    box-shadow: 0 0 8px 4px #000;
  }

  .calculator input {
    width: 100%;
    padding: 20px 15px;
    background: #fff;
    border: 0;
    outline: 0;
    font-size: 20px;
    border-radius: 40px;
    text-align: right;
    transition: .5s;
    box-shadow: 0 0 8px 2px #ddd;
    color: #0e0f2f;
  }

  .calculator input::-webkit-input-placeholder {
    color: #0e0f2f;
  }
  
  .calculator input:hover {
    background: #29b;
    color: #fff;
  }

  .calculator input:focus {
    background: #079;
    color: #fff;
  }

  .calculator .keyboard {
    width: 100%;
    display: flex;
    align-content: center;
    justify-content: center;
    flex-wrap: wrap;
  }

  .calculator .keyboard button {
    box-shadow: 0 0 8px 2px #ddd;
    width: 70px;
    height: 70px;
    margin: 12.5px;
    border: 0;
    outline: 0;
    background: #fff;
    color: #0c0c0e;
    font-size: 50px;
    cursor: pointer;
    border-radius: 20px;
    transition: .5s;
  }

  .calculator .keyboard button:hover {
    color: #fff;
    background: #079;
  }

  .calculator .keyboard .equal {
    width: 160px;
  }

  footer {
    position: fixed;
    bottom: 15px;
    left: 50%;
    transform: translateX(-50%);
    color: #fff;
    font-size: 30px;
  }
</style>
