<template>
  <div>
    <div class="flex111">
      <div class="main">
        <div class="main1">
          <p>Menu</p>
          <p>
            <b-form-input placeholder="Chọn menu" class=""></b-form-input>
          </p>
        </div>
        <div class="main1">
          <p>Hành động</p>
          <p>
            <select class="form-control" v-model="selected">
              <option>Active</option>
              <option>abcc</option>
              <option>abhud</option>
            </select>
          </p>
        </div>
      </div>
      <div class="main">
        <div class="main1">
          <p>Từ ngày</p>
          <p>
            <b-form-input placeholder="Chọn ngày" class=""></b-form-input>
          </p>
        </div>
        <div class="main1">
          <p>Đến ngày</p>
          <p>
            <b-form-input placeholder="Chọn ngày" class=""></b-form-input>
          </p>
        </div>
      </div>
      <div class="main1">
        <p>Tài khoản</p>
        <p>
          <b-form-input placeholder="Tài khoản" class=""></b-form-input>
        </p>
      </div>
      <div class="main23">
        <b-button @click="addItem" variant="success" class="ml-1"
          >Tra cứu</b-button
        >
        <b-button @click="addItem" variant="success" class="ml-1"
          >Làm mới</b-button
        >
        <b-button @click="addItem" variant="success" class="ml-1"
          >Xuất báo cáo</b-button
        >
      </div>
    </div>
    <div class="flex111 mt-1">
      <p class="textp">Danh sách lịch sử tác động hệ thống</p>
      <div>
        <b-table striped hover :items="items"></b-table>
      </div>
    </div>
  </div>
</template>

<script>
import {
  BCard,
  BRow,
  BCol,
  BFormInput,
  BButton,
  BTable,
  BMedia,
  BAvatar,
  BLink,
  BBadge,
  BDropdown,
  BDropdownItem,
  BPagination,
  BTooltip,
} from "bootstrap-vue";
import vSelect from "vue-select";

export default {
  components: {
    BCard,
    BRow,
    BCol,
    BFormInput,
    BButton,
    BTable,
    BMedia,
    BAvatar,
    BLink,
    BBadge,
    BDropdown,
    BDropdownItem,
    BPagination,
    BTooltip,

    vSelect,
  },
  data() {
    return {
      items: [
        { id: '', "Tên menu": "", "Tên người dùng": "","Tài khoản":"","Ngày tác động":"" },        
      ],
    };
  },
  computed: {},
  watch: {},
};
</script>

<style lang="scss" scoped>
.main {
  display: flex;
  justify-content: space-around;
  width: 100%;
}
.main1 {
  width: 49%;
}
.flex111 {
  border: 1px solid gainsboro;
  padding: 10px;
}
.main23 {
  display: flex;
  justify-content: center;
}
.textp{
    font-weight: 600;
}
</style>

<style lang="scss">
@import "@core/scss/vue/libs/vue-select.scss";
</style>
