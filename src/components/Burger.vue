<template>

  <div class="box_burgare class_BURGARE">
    <b> {{ burger.name }} </b>
    <img v-bind:src="burger.url" style="width:300px;height:300px" >
    <ul>
      <li>{{ burger.kcal }}</li>
      <span v-if="burger.gluten==true"><li> Contains Gluten</li></span>
      <span v-if="burger.lactose==true"><li> Contains Lactose</li></span>
      <span v-if="burger.gluten==true"><li> Contains Gluten</li></span>
    </ul>
    <p> {{ burger.text }} </p>
    <div>
      <button v-on:click="addBurger">+</button>
    </div>
    <div>
      <button v-on:click="removeBurger">-</button>
    </div>
    <p> {{ amountOrdered }} </p>
  </div>


</template>

<script>
export default {
  name: 'Burger',
  props: {
    burger: Object
  },
  data: function () {
    return {
      amountOrdered: 0,
    }
  },
  methods: {

    addBurger: function () {
      this.amountOrdered += 1,
      this.$emit('orderedBurger', { name: this.burger.name, amount: this.amountOrdered });
    },

    removeBurger: function () {
      if (this.amountOrderd >0) {
        this.amountOrdered -= 1
      }
      return this.amountOrdered
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
</style>
