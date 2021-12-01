<template lang="">

            <div>
                   
  <b-button v-b-modal.modal-1>Button</b-button>
  <b-modal id="modal-1" title="Sơ đồ thủy lực sông cả" size="xl">
        <div class="all_main">
            <div v-for="val in db" :key="val.id" :class="[`cusoor noname${val.id}`]">
              <div>
                  <div v-if="val.id==1 || val.id==15 || val.id==16 || val.id==12 || val.id==17" :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="https://api.asm.skype.com/v1/objects/0-sa-d2-2eb20f7cda8e1ce944aebf63fb0a7282/views/imgpsh_fullsize_anim" style="width:25px;height:25px"/>
                  </div>
                  <div v-else-if="val.id==9 || val.id==13 || val.id==14 || val.id==24" :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="https://api.asm.skype.com/v1/objects/0-sa-d7-a1e17bfdd323562c1b5280acfc67c78c/views/imgpsh_fullsize_anim" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==6 || val.id==18 || val.id==21 " :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="https://api.asm.skype.com/v1/objects/0-sa-d1-b68984a36d28b823afca8e7e3c186b0d/views/imgpsh_fullsize_anim" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==11 || val.id==19 || val.id==22 || val.id==23 || val.id==25 || val.id==26" :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="https://api.asm.skype.com/v1/objects/0-sa-d4-96f9c7065a2430a85ba588a1a77f5832/views/imgpsh_fullsize_anim" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==20" :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="https://api.asm.skype.com/v1/objects/0-sa-d7-e563a38e2c42a5ffdaaa79c7459d7d5d/views/imgpsh_fullsize_anim" style="width:20px;height:20px"/>
                  </div>
                  <div v-else :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="https://api.asm.skype.com/v1/objects/0-sa-d4-2559dd24d29843f55afba819faf0f71c/views/imgpsh_fullsize_anim" style="width:20px;height:20px"/>
                  </div>
                </div>
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
        { id: 5, kw: "TĐ. Khe bố - 100MW", time_run: "Hoạt động 2013" },
        { id: 6, kw: "TĐ. Nậm mô 1-90MW", time_run: "Dự kiến phát điện 2021" },
        { id: 7, kw: "TĐ. Nậm mô - 38MW", time_run: "Hoạt động 2010" },
        { id: 8, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 9, kw: "TĐ. Bản vẽ", time_run: "Hoạt động 2010" },
        { id: 10, kw: "TĐ. Chỉ khê - 41MW", time_run: "Hoạt động 2017" },
        { id: 11, kw: "TĐ. Quỳ châu", time_run: "(Q, H:1960 -nay)" },
        { id: 12, kw: "TĐ. Nhan Hạc - 59MW", time_run: "Đang hoạt động" },
        { id: 13, kw: "Con cuông", time_run: "(H:1957 -nay)" },

        { id: 14, kw: "Nghĩa Khánh", time_run: "(H, Q:1973 -nay)" },
        { id: 15, kw: "TĐ. Bản Mồng - 42MW", time_run: "Đang xây dựng" },
        { id: 16, kw: "TĐ. Châu Thắng - 14MW", time_run: "Hoạt động năm 2017" },
        { id: 17, kw: "TĐ. Bản Cốc - 18MW", time_run: "Hoạt động năm 2010" },
        { id: 18 }, //Tân kỳ

        { id: 19, kw: "Dừa", time_run: "(Q-H: 1959-nay)" },
        { id: 20}, //đập đô lương
        { id: 21}, //Thanh Liên
        { id: 22, kw: "Yên Thượng", time_run: "( Q-H: 1968 - nay )" },
        { id: 23, kw: "Nam Đàn", time_run: "( Q-H: 1960 - nay )" },
        { id: 24, kw: "Linh Cảm", time_run: "( H: 1959 - nay )" },
        { id: 25, kw: "Sơn Diệm", time_run: "( Q-H: 1961 - nay )" },
        { id: 26, kw: "Hòa Duyệt", time_run: "( Q-H: 1961 - nay )" },
        { id: 26, kw: "TĐ. Ngàn Trươi - 15MW", time_run: "Hoạt động năm 2017" },


        

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
.image {
  margin-left: -4px;
  margin-top: -7px;
  z-index: 100;
}
.fix_noname {
  position: absolute;
  width: 10px;
  height: 10px;
}
.fix_after {
  content: " ";
  top: -130px;
  position: absolute;
  border: 1px solid black;
  z-index: -100;
}
.all_main {
  position: relative;
  width: 1200px;
  height: 2000px;
  border: 1px solid black;
  left: 0px;
}
.cusoor {
  width: 10px;
  height: 10px;
  z-index: 100;
  cursor: pointer;
}
.dis_block1,
.dis_block2,
.dis_block3,
.dis_block9,
.dis_block10,
.dis_block12,
.dis_block16,
.dis_block17,
.dis_block13,
.dis_block19,
.dis_block22,
.dis_block23,
.dis_block25,
.dis_block26,
.dis_block5 {
  width: 200px;
  height: 60px;
  border: 1px solid black;
  margin-left: 20px;
  position: absolute;
}

.dis_block4,
.dis_block6,
.dis_block7,
.dis_block14,
.dis_block15,
.dis_block24,
.dis_block11 {
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
  height: 1900px;
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
  font-weight: bold;
  font-size: 12px;
  color: black;
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
  margin-top: 450px;
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
.noname9::after {
  @extend .fix_after;
  height: 350px;
  left: 180px;
  transform: rotate(90deg);
}
.noname9::before {
  content: "Sông muối nguyên";
  position: absolute;
  height: 350px;
  width: 150px;
  left: 200px;
  top: 25px;
  font-weight: bold;
  font-size: 12px;
  color: black;
}
.noname10 {
  @extend .fix_noname;
  margin-top: 560px;
  left: 600px;
  z-index: 100;
}
.noname10::after {
  @extend .fix_after;
  height: 434px;
  top: -160px;
  left: 222px;
  transform: rotate(90deg);
}
.noname11 {
  @extend .fix_noname;
  margin-top: 612px;
  left: 1000px;
  z-index: 100;
}
.noname11::after {
  @extend .fix_after;
  height: 434px;
  top: -428px;
  left: 38px;
}
.noname12 {
  @extend .fix_noname;
  margin-top: 340px;
  left: 1030px;
  z-index: 100;
}
.noname12::after {
  @extend .fix_after;
  height: 140px;
  top: -140px;
  left: 77px;
  transform: rotate(90deg);
}
.noname12::before {
  content: "Sông Nậm Quang";
  position: absolute;
  z-index: 100;
  width: 50px;
  top: 65px;
  left: 15px;
  font-weight: bold;
  color: black;
  font-size: 12px;
}
.noname13 {
  @extend .fix_noname;
  margin-top: 590px;
  left: 600px;
  z-index: 100;
}
.noname14 {
  @extend .fix_noname;
  margin-top: 612px;
  left: 800px;
  z-index: 100;
}
.noname15 {
  @extend .fix_noname;
  margin-top: 612px;
  left: 900px;
  z-index: 100;
}
.noname18 {
  @extend .fix_noname;
  margin-top: 612px;
  left: 700px;
  z-index: 100;
}
.noname18::after {
  content: "Tân kỳ";
  position: absolute;
  z-index: 100;
  width: 50px;
  top: -30px;
  left: -20px;
  font-weight: bold;
  color: black;
}
.noname15::after {
  content: "Sông Hiếu";
  position: absolute;
  z-index: 100;
  width: 100px;
  top: -21px;
  left: -70px;
  font-weight: bold;
  color: black;
  font-size: 12px;
}
.image18 {
  margin-top: -9px;
}
.noname16 {
  @extend .fix_noname;
  margin-top: 550px;
  left: 1030px;
  z-index: 100;
}
.noname17 {
  @extend .fix_noname;
  margin-top: 264px;
  left: 1147px;
  z-index: 100;
}
.noname17::after {
  content: "Sông Nậm Giải";
  position: absolute;
  z-index: 100;
  width: 80px;
  top: -50px;
  right: 25px;
  font-weight: bold;
  color: black;
  font-size: 12px;
}
.noname19 {
  @extend .fix_noname;
  margin-top: 700px;
  left: 600px;
  z-index: 100;
}
.noname20 {
  @extend .fix_noname;
  margin-top: 750px;
  left: 600px;
  z-index: 100;
}
.noname20::after {
  content: "Đập đô lương";
  position: absolute;
  z-index: 100;
  width: 100px;
  top: -15px;
  right: 5px;
  font-weight: bold;
  color: black;
  font-size: 12px;
}
.noname20::before {
  @extend .fix_after;
  height: 400px;
  top: -140px;
  left: -195px;
  transform: rotate(90deg);
}
.noname21 {
  @extend .fix_noname;
  margin-top: 805px;
  left: 530px;
  z-index: 100;
}
.noname21::after {
  content: "Thanh Liên";
  position: absolute;
  z-index: 100;
  width: 100px;
  top: -20px;
  right: -60px;
  font-weight: bold;
  color: black;
  font-size: 12px;
}
.noname21::before {
  content: "Sông giăng";
  position: absolute;
  z-index: 100;
  width: 100px;
  top: -12px;
  right: 220px;
  font-weight: bold;
  color: black;
  font-size: 12px;
}
.noname22 {
  @extend .fix_noname;
  margin-top: 880px;
  left: 600px;
  z-index: 100;
}
.noname23 {
  @extend .fix_noname;
  margin-top: 1000px;
  left: 600px;
  z-index: 100;
}
.noname23::after {
    @extend .fix_after;
  height: 302px;
  top: -70px;
  left: -147px;
  transform: rotate(90deg);
}
.noname24 {
  @extend .fix_noname;
  margin-top: 1077px;
  left: 510px;
  z-index: 100;
}
.noname24::after {
    @extend .fix_after;
  height: 650px;
  top: -185px;
  left: -207px;
}
.noname25 {
  @extend .fix_noname;
  margin-top: 975px;
  left: 298px;
  z-index: 100;
}
.noname25::after {
  content: "Sông ngàn phố";
  position: absolute;
  z-index: 100;
  width: 100px;
  top: -75px;
  right: -35px;
  font-weight: bold;
  color: black;
  font-size: 12px;
  transform: rotate(90deg);
}
.noname26 {
  @extend .fix_noname;
  margin-top: 1200px;
  left: 298px;
  z-index: 100;
}
</style>