<template lang="">

            <div>
                   
  <b-button v-b-modal.modal-1>Button</b-button>
  <b-modal id="modal-1" title="Sơ đồ thủy lực sông cả" size="xl">
        <div class="all_main">
            <div v-for="val in db" :key="val.id" :class="[`cusoor noname${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                  <div v-if="upHere==val.id" :class="[`dis_block${val.id}`]">
                        <span>{{val.kw}}</span><br />
                        <span>{{val.time_run}}</span>
                  </div>
            </div>
    </div>
  </b-modal>

      </div>
</template>
<script>
import { BButton } from "bootstrap-vue";
import { BModal } from "bootstrap-vue";
export default {
  data() {
    return {
      selected: null,
      upHere: "",
      db: [
        { id: 1, kw: "TĐ. Mỹ lý - 38MW", time_run: "Dự kiến phát điện 2021" },
        { id: 2, kw: "TĐ. Nậm mô - 38MW", time_run: "Hoạt động từ 2013" },
        { id: 3, kw: "TĐ. Nậm nơn - 20MW", time_run: "Dự kiến phát điện 2014" },
        { id: 4, kw: "Thạch giám", time_run: "(H:1987 -nay)" },
        { id: 5, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 6, kw: "TĐ. Nậm mô 1-90MW", time_run: "Dự kiến phát điện 2021" },
        { id: 7, kw: "TĐ. Nậm mô - 38MW", time_run: "Hoạt động 2010" },
        { id: 8, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 9, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 10, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 11, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 12, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 13, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
      ],
    };
  },
  methods: {
    mouseOver: function (x) {
      this.upHere = x;
    },
    mouseOut: function (x) {
      this.upHere = "";
    },
  },
};
</script>


<style lang="scss">
.fix_noname{
  position: absolute;
  width: 10px;
  height: 10px;
  border: 1px solid red;
  background-color: red;
}
.fix_after{
  content: " ";
  top: -130px;
  position: absolute;
  border: 1px solid black;
  z-index: -100;
}
.all_main {
  position: relative;
  width: 1200px;
  height: 1000px;
  border: 1px solid black;
  left: 0px;
}
.cusoor {
  width: 10px;
  height: 10px;
  border: 1px solid red;
  background-color: red;
  z-index: 100;
  cursor: pointer;
}
.dis_block1,
.dis_block2,
.dis_block3,
.dis_block9,
.dis_block10,
.dis_block12,
.dis_block5 {
  width: 200px;
  height: 60px;
  border: 1px solid black;
  margin-left: 20px;
  position: absolute;
}

.dis_block4,.dis_block6,
.dis_block7,.dis_block11{
  width: 200px;
  height: 60px;
  margin-top: -75px;
  margin-left: -170px !important;
  border: 1px solid black;
  margin-left: 20px;
  position: absolute;
}
.noname1 {
  position: relative;
  top: 20px;
  left: 600px;
  z-index: 1;
}
.noname1::after {
  content: " ";
  height: 900px;
  position: absolute;
  border: 1px solid rgb(14, 13, 13);
  left: 51.61%;
  z-index: -1;
}
.noname2 {
  @extend .fix_noname;
  margin-top: 120px;
  left: 600px;
  z-index: 1;
}
.noname2::after {
  @extend .fix_after;
  height: 550px;
  left: -270px;
  transform: rotate(90deg);
}
.noname2::before {
  content: "Sông Nậm Mô";
  position: absolute;
  left: -500px !important;
  top: 125px;
  font-weight: bold;
  z-index: -100;
}

.noname3 {
  @extend .fix_noname;
  margin-top: 200px;
  left: 600px;
  z-index: 100;
  
}
.noname4 {
  @extend .fix_noname;
  margin-top: 260px;
  left: 520px;
  z-index: 100;
}
.noname5 {
  @extend .fix_noname;
  margin-top: 460px;
  left: 600px;
  z-index: 100;
}
.noname6 {
  @extend .fix_noname;
  margin-top: 260px;
  left: 450px;
  z-index: 100;
}
.noname7 {
  @extend .fix_noname;
  margin-top: 260px;
  left: 330px;
  z-index: 100;
}
.noname8 {
  @extend .fix_noname;
  margin-top: 260px;
  left: 250px;
  z-index: 100;
}
.noname9 {
  @extend .fix_noname;
  margin-top: 350px;
  left: 600px;
  z-index: 100;
}
.noname9::after{
  @extend .fix_after;
  height: 350px;
  left: 178px;
  transform: rotate(90deg);
}
.noname9::before{
  content: 'Sông muối nguyên';
  position: absolute;
  height: 350px;
  width: 150px;
  left: 200px;
  top:25px
}
.noname10 {
  @extend .fix_noname;
  margin-top: 560px;
  left: 600px;
  z-index: 100;
}
.noname10::after{
  @extend .fix_after;
  height: 434px;
  top:-160px;
  left: 220px;
  transform: rotate(90deg);
}
.noname11 {
  @extend .fix_noname;
  margin-top: 612px;
  left: 1000px;
  z-index: 100;
}
.noname11::after{
  @extend .fix_after;
  height: 434px;
  top:-428px;
  left: 38px;
}
.noname12 {
  @extend .fix_noname;
  margin-top: 340px;
  left: 1036px;
  z-index: 100;
}
.noname12::after{
  @extend .fix_after;
  height: 140px;
  top:-140px;
  left: 71px;
  transform: rotate(90deg);
}

</style>