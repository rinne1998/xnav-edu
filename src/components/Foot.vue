<template >
  <div id="FootBar">
    <p>
      Copyright © 2022 学习随记 |<a
        href="https://beian.miit.gov.cn/"
        rel="no-referrer"
        target="_blank"
        style="color: #aaaab0; text-decoration: none"
      >
        ICP备案号：湘ICP备20003431号-1
      </a>
      |
      <a
        target="_blank"
        rel="no-referrer"
        href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=43110202000134"
        style="
          display: inline-block;
          text-decoration: none;
          height: 20px;
          line-height: 20px;
          color: #aaaab0;
        "
      >
        湘公网安备 43110202000134号
      </a>
    </p>
  </div>
</template>

<script>
export default {
  name: "FootBar",
};
</script>

<style>
#FootBar {
  text-align: center;
  color: #aaaab0;
  font-size: 10px;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding-bottom: -50px;
}
</style>
