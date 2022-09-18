<template>
  <div class="hello">
    <SiteTitle />
    <div class="TopBar">
      <TimeCard class="hvr-grow" />
      <div id="he-plugin-standard"></div>
      <TipsCard class="hvr-grow" />
    </div>
    <LinkList class="LinkList" />
  </div>
</template>

<script>
import SiteTitle from "./SiteTitle.vue";
import TimeCard from "./TimeCard.vue";
import TipsCard from "./TipsCard.vue";
import LinkList from "./LinkList.vue";
export default {
  name: "HelloWorld",
  components: { SiteTitle, TimeCard, TipsCard, LinkList},
  props: {
    msg: String,
  },
  data() {
    return {
      bg: "url(/imgs/bg.png)",
    };
  },
  mounted() {
    window.WIDGET = {
      CONFIG: {
        layout: "1",
        width: "500",
        height: "175",
        background: "1",
        dataColor: "FFFFFF",
        language: "zh",
        borderRadius: "10",
        key: "02b1248e1a80498d88dc23eaf4da10d8",
      },
    };
    var script = document.createElement("script");
    script.type = "text/javascript";
    script.src =
      "https://widget.qweather.net/standard/static/js/he-standard-common.js?v=2.0";
    document.getElementsByTagName("head")[0].appendChild(script);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.hello {
  width: 100vw;
  height: 100vh;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.TopBar {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  align-items: center;
  transform: translateX(-50%);
  position: absolute;
  left: 50%;
  top: 70px;
}
.LinkList {
  transform: translateX(-50%);
  position: absolute;
  left: 50%;
  top: 260px;
}
</style>
