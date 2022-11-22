<template>
    <div id="calWrap">
        <div class="top">
            <input type="text" v-model="total" />
        </div>
        <div id="keys">
          <div>
            <button v-on:click="key(7)">7</button>
            <button v-on:click="key(8)">8</button>
            <button v-on:click="key(9)">9</button>
            <button v-on:click="key('+')" class="operator">+</button>
          </div>

          <div>
            <button v-on:click="key(6)">6</button>
            <button v-on:click="key(5)">5</button>
            <button v-on:click="key(4)">4</button>
            <button v-on:click="key('-')" class="operator">-</button>
          </div>

          <div>
            <button v-on:click="key(1)">1</button>
            <button v-on:click="key(2)">2</button>
            <button v-on:click="key(3)">3</button>
            <button v-on:click="key('*')" class="operator">*</button>
          </div>

          <div>
            <button v-on:click="key(0)">0</button>
            <button v-on:click="clear()" class="clear">Clear</button>
            <button v-on:click="equal()" class="equal">=</button>
            <button v-on:click="key('/')" class="operator">/</button>
          </div>     
            
        </div>
     </div> 
</template>

<script>

export default {
  name: "Calculator",
  props: {
    msg: String
  },

  data() {
    return { total: 0,};

  },

  methods: {
            key: function(num) {
                 return this.total += num;
            },
            clear: function() {
                return this.total = 0;
            },
            equal: function() {
                 let equal = this.total;
                return this.total = eval(equal);
            }         
  }
  
  

  //end js
};
</script>

<style scoped>

body #calWrap {
  background-color: #5d7fa3;
  border-radius: 23px;
  margin: auto;
  padding: 25px;
  width: 500px;
  display: table;
}
body .top input {
  height: 80px;
  width: 100%;
  font-size: 35px;
  font-weight: bolder;
  border-radius: 4px;
  margin: 0 0 14px 0;
  border: 0;
  padding: 0 1em;
  box-shadow: 0px 4px rgba(0, 0, 0, 0.2);
}

#keys {
  display: flex;
  flex-direction: column;
}

#keys div {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
#keys button {
  flex:1;
  cursor: pointer;
  font-weight: bold;
  text-align: center;
  line-height: 2em;
  background: white;
  font-size: 35px;
  font-weight: bolder;
  border-radius: 3px;
  box-shadow: 0px 4px rgba(0, 0, 0, 0.2);
  transition: all 0.2s ease;
}
#keys button:hover {
  background-color: #D6D6D6;
}
#keys .zero {
  width: 138px !important;
}

#keys .equal {
  background-color: #0084ff !important;
}

#keys .equal:hover {
  background-color: #618db6 !important;
  font-size: 22px;
}

#keys .operator:hover {
  background-color: #77bb95 !important;
  font-size: 22px;
}

#keys .operator {
  background-color: #00ff73 !important;
}
 #keys .clear {
  background-color: #ffd900 !important;
  font-size: 20px;
}

 #keys .clear:hover {
  background-color: #cfc069 !important;
  font-size: 18px;
}

</style>
