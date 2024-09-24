<script>
  export default {
    name: 'App',
    
    data() {
      return {
        inputStr: '',
        result: ''
      }
    },

    methods: {
      updateDisplay(val) {
        this.inputStr = this.inputStr + val
      },
      calculate () {
        this.result = eval(this.inputStr)
        console.log(this.result)
        this.inputStr = this.result
      },

      clearDisplay() {
        this.inputStr = ''
      }
    },

    
  }
</script>

<template>
    <body>
      <div class="container p-5">
        <div class="display">
          <form action="form-group" @submit.prevent="calculate" >
            <input class="display" type="text" v-model="inputStr">
            <input class="equal" type="submit" value="=" >
          </form>
        </div>



        <div class="buttons">

          <div class="row">
            <div class="col-auto">
              <button @click="() => updateDisplay('+')" class="btn">+</button>
              <button @click="() => updateDisplay('-')" class="btn">-</button>
              <button @click="() => updateDisplay('*')" class="btn">*</button>
              <button @click="() => updateDisplay('/')" class="btn">/</button>
              
            </div>
          </div>

          <div class="row">
            <div class="col-auto">
              <button @click="() => updateDisplay('1')" class="btn">1</button>
              <button @click="() => updateDisplay('2')" class="btn">2</button>
              <button @click="() => updateDisplay('3')" class="btn">3</button>
              <button class="btn" @click="clearDisplay" >C</button>
            </div>
          </div>

          <div class="row">
            <div class="col-auto">
              <button @click="() => updateDisplay('4')" class="btn">4</button>
              <button @click="() => updateDisplay('5')" class="btn">5</button>
              <button @click="() => updateDisplay('6')" class="btn">6</button>
              <button @click="() => updateDisplay('0')" class="btn">0</button>
            </div>
          </div>

          <div class="row">
            <div class="col-auto">
              <button @click="() => updateDisplay('7')" class="btn">7</button>
              <button @click="() => updateDisplay('8')" class="btn">8</button>
              <button @click="() => updateDisplay('9')" class="btn">9</button>
              <button @click="() => updateDisplay('.')" class="btn">.</button>
            </div>
          </div>
        </div>
      </div>
    </body>
</template>

<style scoped>

.container {
  width: 100%;
  margin: auto;
  position: relative;
  left: 25%;
}

  .btn {
    margin: 16px;
    width: 50px;
    height: 50px;
    border-radius: 8px;
    border: none;
  }

  .equal {
    width: 55px;
    height: 45px;
    background-color: rgb(233, 190, 1);
    border-style: none;
    border-radius: 8px;
    font-size: 20px;
    color: white;
    position: absolute;
    margin-left: 1.5rem;
  }

  .display {
    height: 50px;
    width: 85%;
    border-radius: 8px;
    margin-bottom: 8px;
  }

</style>
