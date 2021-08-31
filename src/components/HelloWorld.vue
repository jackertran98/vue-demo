<template>
  <div class="hello">
    <Table :data1="task" />
  </div>
</template>

<script>
import Table from "./table.vue";

export default {
  name: "HelloWorld",
  components: {
    Table,
  },
  data() {
    return {
      task: [
        { name: "dan", age: 18, id: 25 },
        { name: "viet", age: 29, id: 26 },
        { name: "duc", age: 49, id: 0 },
        { name: "kim", age: 53, id: 1 },
        { name: "nam", age: 6, id: 3 },
        
      ],
      data: [],
    };
  },
  methods: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
