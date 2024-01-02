<script>
export default {
  data() {
    return {
      array: [1, 3, 5, 2, 10, 6, 4, 9],
      filteredArray: []
    };
  },
  methods:{
    getFilteredNumbers(isEven){
      this.filteredArray = [];
      for (let i = 0; i < this.array.length; i++){
        const num = this.array[i];
        if ((isEven && num % 2 === 0) || (!isEven && num % 2 !== 0)){
          this.filteredArray.push(num);
        }
      }
    }
  }
}
</script>

<template>
 <div id="app">
    <button @click="getFilteredNumbers(true)">Array Pari</button>
    <button @click="getFilteredNumbers(false)">Array Dispari</button>
    <div>
      <h3>Risultato:</h3>
      <p v-if="filteredArray.length > 0">{{ filteredArray.join(', ') }}</p>
      <p v-else>Nessun numero trovato</p>
    </div>
  </div>
</template>


