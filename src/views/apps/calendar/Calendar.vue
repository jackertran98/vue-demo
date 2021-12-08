<template lang="">
            <div>
  <b-button v-b-modal.modal-1>Button1</b-button>
  <b-modal id="modal-1" title="Sơ đồ thủy lực sông cả" size="xl">
        <div class="all_main">
            <div v-for="val in db" :key="val.id" :class="[`cusoor noname${val.id}`]">
              <div>
                  <div v-if="val.id==1 || val.id==15 || val.id==16 || val.id==12 || val.id==17 || val.id==27 || val.id==29 || val.id==8" :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="@/assets/images/pages/sao_to.png" style="width:25px;height:25px"/>
                  </div>
                  <div v-else-if="val.id==9 || val.id==13 || val.id==14 || val.id==24 || val.id==28 || val.id==30 || val.id==32 " :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="@/assets/images/pages/tam_giac.png" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==18 || val.id==21 " :class="[`image image${val.id}`]">
                      <img src="@/assets/images/pages/tam_giac_do.png" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==18 || val.id==21 " :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="@/assets/images/pages/sao_xanh.png" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==11 || val.id==19 || val.id==22 || val.id==23 || val.id==25 || val.id==26 || val.id==33 || val.id==6"  :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="@/assets/images/pages/tam_giac_do_vien.png" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==20 || val.id==31" :class="[`image image${val.id}`]">
                      <img src="@/assets/images/pages/bon.png" style="width:20px;height:20px"/>
                  </div>
                  <div v-else :class="[`image image${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="@/assets/images/pages/sao_xanh.png" style="width:20px;height:20px"/>
                  </div>
                </div>
                  <div v-if="upHere==val.id" :class="[`noway_dis dis_block${val.id}`]">
                        <span class="span_id">{{val.kw}}</span><br />
                        <span>{{val.time_run}}</span>
                  </div>
            </div>
            <div class="chu_thich">
                  <p class="chu_giai">Chú giải</p>
                  <div class="child_ct">
                      <div class="child_img">
                          <img src="@/assets/images/pages/sao_to.png" style="width:25px;height:25px"/>
                      </div>
                      <div>
                          <p>Công trình thủy điện đang xây dựng</p>
                      </div>
                  </div>
                  <div class="child_ct">
                      <div class="child_img">
                          <img src="@/assets/images/pages/tam_giac.png" style="width:20px;height:20px"/>
                      </div>
                      <div>
                          <p>Trạm thủy văn đang đo</p>
                      </div>
                  </div>
                  <div class="child_ct">
                      <div class="child_img">
                          <img src="@/assets/images/pages/sao_xanh.png" style="width:20px;height:20px"/>
                      </div>
                      <div>
                          <p>Công trình thủy điện</p>
                      </div>
                  </div>
                  <div class="child_ct">
                      <div class="child_img">
                         <img src="@/assets/images/pages/tam_giac_do_vien.png" style="width:20px;height:20px"/>
                      </div>
                      <div>
                          <p>Trạm thủy văn đề xuất nâng cấp</p>
                      </div>
                  </div>
                  <div class="child_ct">
                      <div class="child_img">
                          <img src="@/assets/images/pages/bon.png" style="width:20px;height:20px"/>
                      </div>
                      <div>
                          <p>Đập dâng</p>
                      </div>
                  </div>
                  <!-- <div class="child_ct">
                      <div class="child_img">
                          <img src="https://api.asm.skype.com/v1/objects/0-sa-d4-ab3d1102d3cbdd735eef924218e26a24/views/imgpsh_fullsize_anim" style="width:20px;height:20px"/>
                      </div>
                      <div>
                          <p>Trạm thủy văn đang đo</p>
                      </div>
                  </div>
                  <div class="child_ct">
                      <div class="child_img">
                          <img src="https://api.asm.skype.com/v1/objects/0-sa-d7-5b59d05dceaa6ec37ed41f0b04445859/views/imgpsh_fullsize_anim" style="width:25px;height:25px"/>
                      </div>
                      <div>
                          <p>Trạm thủy văn đang đo</p>
                      </div>
                  </div> -->
            </div>
            
    </div>
    
  </b-modal>



  <b-button v-b-modal.modal-2>Button2</b-button>
  <b-modal id="modal-2" title="Sơ đồ thủy lực sông Vu Gia Thu Bồn" size="xl">
        <div class="all_main">
            <div v-for="val in db_thubon" :key="val.id" :class="[`cusoor thubon${val.id}`]">
              <div>
                  <div v-if="val.id==1 || val.id==3 || val.id==4 || val.id==6 || val.id==7 || val.id==8 || val.id==12 || val.id==13" :class="[`image_tb image_tb${val.id}`]">
                      <img src="@/assets/images/pages/sao_xanh.png" style="width:25px;height:25px"/>
                  </div>
                  <div v-else-if="val.id==2 || val.id==5 || val.id==9 || val.id==11 " :class="[`image_tb image_tb${val.id}`]" @mouseover="mouseOver(val.id)" @mouseout="mouseOut()">
                      <img src="@/assets/images/pages/tam_giac_do.png" style="width:20px;height:20px"/>
                  </div>
                  <div v-else-if="val.id==10 || val.id==14"  :class="[`image_tb image_tb${val.id}`]">
                      <img src="@/assets/images/pages/tam_giac.png" style="width:20px;height:20px"/>
                  </div>
                </div>
                  <div v-if="upHere==val.id" :class="[`noway_dis dis_block_thubon${val.id}`]">
                        <span class="span_id">{{val.name}}</span>
                        <span>{{val.content}}</span>
                  </div>
            </div>


            <div class="song_han"></div>
            <div class="an_trach">
                  <p>Sông Bầu Sơn</p>
                  <div class="ha_thanh"></div>
            </div>
            <div class="la_tho"></div>
            <div class="thanh_quyt"></div>
            <div class="song_co_ca"></div>
            <div class="cua_dai"></div>
            <div class="song_ba_ren">
                <p>Sông Ba Ren</p>
            </div>
            <div class="song_vu_gia"></div>

            <div class="song_khang">
                <p>Sông Khang</p>
            </div>
            <div class="son_tan"></div>
            <div class="song_tranh"></div>

            
          </div>
    
  </b-modal>

      </div>
</template>
<script>
import {
  BForm,
  BFormGroup,
  BFormInput,
  BRow,
  BCol,
  BButton,
} from "bootstrap-vue";
import { BModal } from "bootstrap-vue";
import soapRequest from 'easy-soap-request';
import axios from 'axios';
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
        { id: 20 }, //đập đô lương
        { id: 21 }, //Thanh Liên
        { id: 22, kw: "Yên Thượng", time_run: "( Q-H: 1968 - nay )" },
        { id: 23, kw: "Nam Đàn", time_run: "( Q-H: 1960 - nay )" },
        { id: 24, kw: "Linh Cảm", time_run: "( H: 1959 - nay )" },
        { id: 25, kw: "Sơn Diệm", time_run: "( Q-H: 1961 - nay )" },
        { id: 26, kw: "Hòa Duyệt", time_run: "( Q-H: 1961 - nay )" },
        { id: 27, kw: "TĐ. Ngàn Trươi - 15MW", time_run: "Hoạt động năm 2017" },
        { id: 28, kw: "Chu Lễ" }, //Chu lễ
        { id: 29, kw: "TĐ. Hồ Hô - 14MW", time_run: "Hoạt động năm 2013" },
        { id: 30, kw: "Chợ Tràng", time_run: "( H:1961 - nay )" },
        { id: 31 }, //Cổng trung lương
        { id: 32 }, //Xuân hồng
        { id: 33, kw: "Cửa Hội", time_run: "( H:1961 - nay )" },
      ],
      db_thubon:[
          {id:1},  //td.song bung2
          {id:2,name:'Hồ Sông Bung 2:',content:' Giám sát lượng nước dòng chính đến hồ Sông Bung 4 và giám sát lượng nước từ hồ Sông Bung 2'},
          {id:3},  //td.song bung4
          {id:4},  //td.a vuong
          {id:5,name:'Hồ Sông A Vương:',content:' Giám sát lượng nước đến Hồ A Vương'},
          {id:6},  //td.song bung4a
          {id:7},   //td.song bung5
          {id:8},   //td.song bung6
          {id:9,name:'Thác Cạn:',content:' Giám sát lượng nước sông Bung trước khi nhập với sông Đăk mi thành dòng Vu Gia, làm cơ sở điều hành các hồ trên thượng lưu sông Bung'},
          {id:10},   //hoi khach
          {id:11,name:'Hà Tân',content:' Giám sát lượng nước sông con trước khi nhập vào sông Vu Gia, làm cơ sở vận hành các hồ thủy điện trên 2 nhánh suối chính trên thượng nguồn'},
          {id:12},   //td.song con2  
          {id:13},   //td.song con1
          {id:14},   //ai nghia
          {id:15},   //dap an trach
          {id:16,name:'Cẩm lệ',content:'(H.1975-nay)'},
          {id:17},    //song han
          {id:18},   //dap ha thanh
          {id:19},   //dap bau nit


      ]
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
  created(){
      var data = '<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.ws.um.carbon.wso2.org">\r\n   <soapenv:Header/>\r\n   <soapenv:Body>\r\n      <ser:getRoleListOfUser>\r\n         <!--Optional:-->\r\n         <ser:userName>administrator</ser:userName>\r\n      </ser:getRoleListOfUser>\r\n   </soapenv:Body>\r\n</soapenv:Envelope>';

var config = {
  method: 'post',
  url: 'https://identity.kttv.gov.vn:9443/services/RemoteUserStoreManagerService',
  headers: { 
    'Accept-Encoding': ' gzip,deflate', 
    'Content-Type': ' text/xml;charset=UTF-8', 
    'SOAPAction': ' "urn:getRoleListOfUser"', 
    'Content-Length': ' 343', 
    'Host': ' identity.kttv.gov.vn:9443', 
    'Connection': ' Keep-Alive', 
    'User-Agent': ' Apache-HttpClient/4.5.5 (Java/12.0.1)', 
    'Cookie': ' JSESSIONID=E6BD7131C11688272303088995A30CDC; JSESSIONID=447067EDB66C8DE081BBAF0F42655FB8', 
    'Authorization': ' Basic YWRtaW46YWRtaW4='
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
}); 
  }
};
</script>


<style lang='scss'>
  @import './button1.scss';
  @import './button2.scss';
</style>