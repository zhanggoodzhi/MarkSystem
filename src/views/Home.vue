<template>
  <div class="home">
    <!-- <img src="../assets/logo.png"> -->
    <img src="/img/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <div class="test-box vms">
      <div class="test-div"></div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import axios from "axios";

export default {
  mounted: () => {
    axios
      .post("http://zhanggoodzhi.top/account/login", {
        account: "Fred",
        psd: "Flintstone"
      })
      .then(function(response) {
        console.log(response);
      })
      .catch(function(error) {
        console.log(error);
      });
  },
  name: "home",
  components: {
    HelloWorld
  }
};
</script>

<style scoped lang="less">
.home {
  .test-box {
    width: 100px;
    height: 100px;
    background: red;
    .test-div {
      vertical-align: middle;
      width: 20px;
      height: 20px;
      display: inline-block;
      background: black;
    }
  }
}
</style>
