<template lang="">
  <div>
    <div>
      <button
        class="btn btn-warning"
        @click="isCheck = !isCheck"
        v-show="!isCheck"
      >
        Thêm mới
      </button>
      <div>
        <div v-show="isCheck">
          <input type="text" v-model="name" />Tên
          <input type="text" v-model="age" />Tuổi
          <p>{{ id }}</p>
          <button @click="[addHuman(), (isCheck = !isCheck)]">
            Thêm mới +
          </button>
        </div>
      </div>
      <input type="text" v-model="valueChange" />
      <button @click="handChange()">tìm</button>
    </div>
    <b-table-simple>
      <b-tr>
        <b-th>Tên</b-th>
        <b-th>Tuổi</b-th>
        <b-th>Xóa</b-th>
      </b-tr>
      <b-tr v-for="(value, key) in dataMain" :key="key">
        <b-td>{{ value.name }}</b-td>
        <b-td>{{ value.age }}</b-td>
        <b-td>
          <buton @click="handsome(value.id)">Xóa</buton>
        </b-td>
      </b-tr>
    </b-table-simple>
  </div>
</template>
<script>
export default {
  props: ["data1"],
  data() {
    return {
      name: "",
      age: "",
      id: "",
      valueChange: "",
      isCheck: false,
      dataMain: this.data1,
    };
  },
  mounted() {
    this.handsome = (a) => {
      return (this.dataMain = this.dataMain.filter((val) => val.id != a));
    };
    this.addHuman = () => {
      if (this.name == "") {
        alert("vui lòng nhập thông tin");
        return;
      }
      return (this.dataMain = [
        ...this.dataMain,
        { name: this.name, age: this.age, id: Math.random() },
      ]);
    };
    this.handChange = () => {
      if (this.valueChange != "") {
        return (this.dataMain = this.dataMain.filter(
          (val) => val.name == this.valueChange
        ));
      } else {
        return this.dataMain;
      }
    };

    // this.$emit("handsome", value);
  },
};
</script>
<style lang=""></style>
