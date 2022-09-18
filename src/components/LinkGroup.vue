<template>
  <div class="LinkGroup">
    <div class="t"><img :src="Linksdata.icon" /><span> {{Linksdata.category}}</span></div>
    <div class="links">
      <div v-for="item in Linksdata.links" :key="item.name"><LinkCard :linkdata="item" /></div>
      <i /> <i /> <i /> <i /> <i /> <i />
    </div>
  </div>
</template>

<script>
import LinkCard from "./LinkCard";
export default {
  name: "LinkGroup",
  components: { LinkCard },
  data() {
    return {};
  },
  props: {
    Linksdata: Object,
  },
};
</script>

<style scoped>
.LinkGroup {
  margin-top: 15px;
  margin-left: 5px;
  margin-right: 5px;
  font-family: OPPOSans;
  width: 100%;
  background: #fff;
  border-radius: 10px;
  font-weight: 600;
  text-align: left;
  font-size: 16px;
  color: #000;
}
.has_link {
  padding-bottom: 10px;
  padding-left: 36px;
  padding-top: 14px;
  border-bottom: 1px solid #f1f4f9;
  line-height: 16px;
  font-size: 15px;
  text-align: left;
}
.t img {
  width: 18px;
  margin-left: 10px;
}
.t span {
  margin-left: 8px;
}
.t {
  margin-top: 2px;
  padding: 10px;
  border-bottom: 1px solid #e1eaf8;
  display: flex;
  align-items: center;
}
.links {
  padding-bottom: 20px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
.links > i {
  height: 0px;
  width: 200px;
  margin-right: 5px;
  margin-left: 5px;
}
</style>
