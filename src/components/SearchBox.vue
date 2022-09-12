<template>
  <div class="SearchBox">
    <div class="search">
      <input
        placeholder="搜索一下……"
        v-model="searchtext"
        @keyup.enter="goto(searchtext)"
      /><button @click="goto(searchtext)">
        <img src="/imgs/baidu.svg" />
      </button>
      <div>
        <button @click="gotobili(searchtext)" style="background: #ff709f">
          <img src="/imgs/BILIBILI_LOGO.svg" style="width: 35px" />
        </button>
        <button @click="gotowk(searchtext)" style="background: #0ab885">
          <img src="/imgs/wk.png" style="width: 20px" />
        </button>
        <button @click="goto(searchtext)">
          <img src="/imgs/search.svg" />
        </button>
        <button @click="goto(searchtext)">
          <img src="/imgs/search.svg" />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchBox",
  data() {
    return {
      searchtext: "",
    };
  },
  methods: {
    goto: function (url) {
      window.open(
        "https://www.baidu.com/s?ie=utf-8&f=8&rsv_bp=1&tn=baidu&wd=" + encodeURIComponent(url),
        "_blank"
      );
    },
    gotobili: function (url) {
      window.open(
        "https://search.bilibili.com/all?from_source=webtop_search&spm_id_from=333.1007&search_source=5&keyword=" + encodeURIComponent(url),
        "_blank"
      );
    },
    gotowk: function (url) {
      window.open(
        "https://wenku.baidu.com/search?lm=0&od=0&fr=top_home&ie=utf-8&word=" + encodeURIComponent(url),
        "_blank"
      );
    },
  },
};
</script>

<style>
.SearchBox {
  display: block;
  font-family: OPPOSans;
  height: 100px;
}
.search {
  width: 1200px;
  height: 50px;
  transform: translateX(-50%);
  top: 35px;
  left: 50%;
  position: absolute;
  border-radius: 5px;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.search > input {
  width: 790px;
  background: #fff;
  height: 45px;
  border: none;
  border-radius: 5px 0 0 5px;
  margin-right: 0;
  padding: 0;
  padding-left: 15px;
  font-size: 14px;
}
.search > input:focus {
  box-shadow: none;
  border: none;
  outline: none;
}
.search > button {
  width: 60px;
  background: #597bf7;
  height: 45px;
  border-radius: 0 5px 5px 0;
  margin-left: -5px;
  border: none;
  cursor: pointer;
}
.search > button > img {
  width: 19px;
  height: 19px;
  margin-top: 4px;
}
input::-webkit-input-placeholder {
  /* WebKit browsers*/
  color: rgb(167, 167, 167);
  font-size: 14px;
}
input:-moz-input-placeholder {
  /* Mozilla Firefox 4 to 18*/
  color: rgb(167, 167, 167);
  font-size: 14px;
}
input::-moz-input-placeholder {
  /* Mozilla Firefox 19+*/
  color: rgb(167, 167, 167);
  font-size: 14px;
}

input:-ms-input-placeholder {
  /* Internet Explorer 10+*/
  color: rgb(167, 167, 167);
  font-size: 14px;
}
.search > div {
  display: flex;
}
.search > div > button {
  width: 55px;
  height: 45px;
  border-radius: 5px;
  margin-left: 10px;
  border: none;
  cursor: pointer;
}
.search > div > button > img {
  margin-top: 4px;
}
</style>
