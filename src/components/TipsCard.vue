<template>
  <div class="TipsCard">
    <div class="title">
      <img src="/imgs/tips.svg" />
      <div class="title-text">我们需要帮助！</div>
    </div>
    <div class="content">
      本站于9月18日紧急上线，旨在收集网络上的教学资源，如果你有想法或者网站分享，请联系开发者QQ：3241312613，或发送邮件至33@aige.link，谢谢你的支持！<br />
      <div style="margin-top: 10px"></div>
      请使用快捷键 <em>"Ctrl"</em> + <em>"+"</em> 或 <em>"Ctrl"</em> +
      <em>"-"</em> 调整缩放，以达到最好的浏览效果！
    </div>
  </div>
</template>

<script>
export default {
  name: "TipsCard",
};
</script>

<style>
.TipsCard {
  font-family: OPPOSans;
  width: 320px;
  height: 175px;
  background: linear-gradient(
    270deg,
    rgba(168, 237, 234, 1) 0%,
    rgba(254, 214, 227, 1) 100%
  );
  border-radius: 10px;
  margin-left: 20px;
  font-weight: 600;
  text-align: left;
  font-size: 14px;
  color: #000;
}
.title {
  margin-top: 14px;
  display: flex;
  margin-left: 20px;
}
.title img {
  width: 15px;
}
.title div {
  margin-left: 5px;
}
.content {
  margin-top: 8px;
  margin-left: 20px;
  margin-right: 20px;
}
</style>
