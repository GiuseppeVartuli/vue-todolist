<script>
export default {
  name: "App",
  data() {
    return {
      list: [
        { text: "Carne", done: false },
        { text: "Frutta", done: false },
        { text: "Verdura", done: false },
        { text: "Biscotti", done: false },
        { text: "Latte", done: false },
        { text: "Pesce", done: true },
        { text: "Caffè", done: false },
        { text: "Cereali", done: false },
        { text: "Formaggi", done: false },
      ],
    };
  },
  methods: {
    deleteFunction(index) {
      this.list.splice(index, 1);
    },
  },
};
</script>

<template>
  <div>
    <h1>Lista della spesa:</h1>
    <ul v-if="list.length > 0">
      <li v-for="(item, index) in list" :class="item.done ? 'done' : ''">
        {{ item.text }} <button @click="deleteFunction(index)">X</button>
      </li>
    </ul>
    <p v-else>Hai il frigo pieno!</p>
  </div>
</template>

<style>
.done {
  text-decoration: line-through;
}

button {
  margin-left: 30px;
}
</style>
