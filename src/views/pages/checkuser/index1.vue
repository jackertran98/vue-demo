<template lang="">
<div class="root_main">
    <div class="child_">
        <div class="root_child" @click="login1">
            <div class='imgec'>
                <img src="@/assets/images/logo/menu1.png" />
            </div>
            <div class="textmac">
                <p>Tài nguyên nước</p>
            </div>
        </div>
        <div class="root_child">
            <div class='imgec'>
                <img src="@/assets/images/logo/menu2.png" />
            </div>
            <div class="textmac">
                <p>Đo đạc bản đồ</p>
            </div>
        </div>
        <div class="root_child">
            <div class='imgec'>
                <img src="@/assets/images/logo/menu3.png" />
            </div>
            <div class="textmac">
                <p>Biến đổi khí hậu</p>
            </div>
        </div>
        <div class="root_child">
            <div class='imgec'>
                <img src="@/assets/images/logo/menu4.png" />
            </div>
            <div class="textmac">
                <p>Viễn thám</p>
            </div>
        </div>
        
        </div>
  </div>
</template>
<script>
import { BookOpenIcon } from "vue-feather-icons";
import { ClipboardIcon } from "vue-feather-icons";
import { CommandIcon } from "vue-feather-icons";
import { FolderIcon } from "vue-feather-icons";
import useJwt from "@/auth/jwt/useJwt";
import { initialAbility } from "@/libs/acl/config";

// import core from '../../../assets/images/pages/login-v2-dark.svg'
export default {
  components: {
    BookOpenIcon,
    ClipboardIcon,
    CommandIcon,
    FolderIcon,
  },
  methods: {
    logout() {
      // Remove userData from localStorage
      // ? You just removed token from localStorage. If you like, you can also make API call to backend to blacklist used token
      localStorage.removeItem(useJwt.jwtConfig.storageTokenKeyName);
      localStorage.removeItem(useJwt.jwtConfig.storageRefreshTokenKeyName);

      // Remove userData from localStorage
      localStorage.removeItem("userData");

      // Reset ability
      this.$ability.update(initialAbility);

      // Redirect to login page

      if (confirm("Bạn chắc chắn muốn đăng xuất !")) {
        return this.$router.push({ name: "auth-login" });
      }
    },
    login1() {
      let routeData = this.$router.resolve({ name: "dashboard-ecommerce" });
      window.open(routeData.href);
    },
    login2() {
      let routeData = this.$router.resolve({ name: "error-404" });
      window.open(routeData.href);
    },
  },
};
</script>

<style lang="scss">
.root_main {
  background-image: url("https://lgsp.monre.gov.vn/static/media/007_Vectordepvn_trongdong-02.55d18e0f.svg");
  background-position: center center;
  background-repeat: no-repeat;
  background-color: #539335;
  height: 100vh;
}
.child_{
    position: relative;
  top: 25%;
    margin: 0px auto;
    width: 500px;
    display: flex;
  justify-content:space-around;
}
.root_child{
    background-color: #fff;
    padding:60px;
    border-radius: 4px;
    text-align: center;
    width: 250px;
    margin-right: 25px;
    height: 300px;
    .textmac{
        margin-top: 45px;
        font-weight: 600;
    }
}
.root_child:hover {
  margin-top: 15px;
  cursor: pointer;
  color: black;
  .icon_hta {
    color: black;
  }
}
</style>