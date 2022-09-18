<template>
  <div class="link-card hvr-grow">
    <a :href="linkdata.link" target="_blank">
      <div class="title">
        <img :src="linkdata.icon" /> <span>{{ linkdata.name }}</span>
      </div>
      <div class="intro">
        <span>{{ linkdata.intro }}</span>
      </div>
      <img src="/imgs/arrow.svg" />
      <div class="tags">
        <span v-for="(t, i) in linkdata.tags" :key="i">{{ t }}</span>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  name: "LinkCard",
  props: {
    linkdata: Object,
  },
  data() {
    return {
      currentDate: new Date(),
    };
  },
  methods: {
    goto: function (url) {
      window.open(url, "_blank");
    },
  },
};
</script>

<style scoped>
.link-card {
  margin-top: 20px;
  display: block;
  border-radius: 8px;
  background: #fff;
  width: 200px;
  height: 120px;
  margin-right: 5px;
  margin-left: 5px;
  box-shadow: 1px 3px 8px 0px rgb(0 0 0 / 3%);
  border: solid 1px #f0f0f0;
  cursor: pointer;
  -moz-user-select: none;
  -khtml-user-select: none;
  user-select: none;
  z-index: 999;
}
.link-card > a > img {
  width: 23px;
  position: absolute;
  right: 8px;
  top: 38%;
}
a {
  text-decoration: none;
  color: #000;
}
.title img {
  width: 30px;
  border-radius: 50%;
}
.title {
  margin-top: 15px;
  display: flex;
  flex-direction: row;
  align-items: center;
}
.title span {
  font-size: 18px;
  margin-left: 10px;
}
.intro {
  font-weight: 500;
  padding-top: 11px;
  color: rgb(114, 112, 112);
  padding-left: 20px;
  font-size: 15px;
}
.tags {
  position: absolute;
  bottom: 10px;
  width: 100%;
  transform: scale(0.85);
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: flex-start;
  margin-left: -2px;
}
.tags > span {
  font-weight: 500;
  padding: 4px;
  font-size: 13px;
  border-radius: 5px;
  background: #3aa775;
  color: #fff;
  margin-left: 5px;
}
</style>
