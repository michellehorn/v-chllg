<template>
  <div class="coins">
    <h1>Coin Challenge</h1>
    <input type="number" v-model="numberX">
    <h4 v-if="arrayR.length > 0">{{arrayR}}</h4>
    <button @click="getValue">Criar array</button>
  </div>
</template>
<script>
export default {
  name: "Coin",
  data: () => ({
    numberX: 0,
    coins: [2, 1, 0.5, 0.2, 0.1, 0.05, 0.02, 0.01],
    arrayR: []
  }),
  methods: {
    getValue() {
      this.arrayR = [];
      let rest = this.numberX;
      for (let i = 0; i <= this.coins.length; i++) {
        if (rest >= this.coins[i]) {
          do {
            this.arrayR.push(this.coins[i]);
            rest = rest - this.coins[i];
          } while (rest >= this.coins[i]);
        }
      }
    }
  }
};
</script>
