<template>
  <div id="app">
    <!-- mutation -->
    <button @click="decrementCount({amount: 2})">-</button>
    <span>{{count}}</span>
    <button @click="incrementCount">+</button>
  </div>
</template>

<script>
import Count from "./components/Count";
import { mapState, mapGetters, mapMutations } from "vuex";

export default {
  name: "app",
  components: {
    Count
  },
  computed: mapGetters([
    "count",
    "completedTodos",
    "completedTodosCount",
    "getTodosById"
  ]),
  methods: mapMutations(["incrementCount", "decrementCount"])
  // methods: {
  //   increment() {
  //     // 调用 mutations 里的 incrementCount
  //     this.$store.commit("incrementCount");
  //   },
  //   decrement(n) {
  //     // 调用 mutations 里的 decrementCount
  //     this.$store.commit("decrementCount", n);
  //   }
  // }
  // computed: {
  //   count() {
  //     return this.$store.getters.count;
  //   },
  //   completedTodos() {
  //     return this.$store.getters.completedTodos;
  //   },
  //   completedTodosCount() {
  //     return this.$store.getters.completedTodosCount;
  //   },
  //   getTodosById() {
  //     return this.$store.getters.getTodosById;
  //   }
  // }
};
</script>

<style scoped>
</style>
