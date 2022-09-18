<template>
  <div class="LinkList">
      <SearchBox />
    <div class="groups" v-for="item in categories" :key="item.name">
      <LinkGroup :Linksdata="item"/>
    </div>
    <FootBar />
  </div>
</template>

<script>
import axios from "axios";
import LinkGroup from "./LinkGroup.vue";
import SearchBox from "./SearchBox.vue"
import FootBar from "./Foot.vue";
export default {
  name: "LinkList",
  components: { LinkGroup,SearchBox ,FootBar},
  data() {
    return {
        categories:""
    };
  },
  mounted(){
      var _this = this
      axios.get("/data.json").then((resp)=>{
        _this.categories = resp.data.categories
      })
  }
};
</script>

<style>
.LinkList {
  font-family: OPPOSans;
  width: 95%;
  background: linear-gradient(
    270deg,
    rgba(168, 237, 234, 1) 0%,
    rgba(254, 214, 227, 1) 100%
  );
  border-radius: 10px;
  font-weight: 600;
  text-align: left;
  font-size: 14px;
  color: #000;
  padding-bottom: 40px;
}
.groups {
  margin: 0 auto;
  width: 98%;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: center;
  align-items: center;
}
</style>
