<template>
  <div class="TimeCard">
    <div class="real-time">19:19:10</div>
    <div class="real-date">2022年11月11日</div>
    <div class="real-week-info">
      <div class="real-week">周日</div>
      <div class="real-week-of-year">第37周</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TimeCard",
};
</script>

<style>
.TimeCard {
  width: 320px;
  height: 175px;
  background: linear-gradient(
    135deg,
    rgba(223, 255, 205, 1) 0%,
    rgba(144, 249, 196, 1) 48%,
    rgba(57, 243, 187, 1) 100%
  );
  border-radius: 10px;
  margin-right: 20px;
}
.real-time {
  font-size: 60px;
  font-weight: 900;
  letter-spacing: 0px;
  line-height: 0px;
  color: rgba(0, 0, 0, 1);
  text-align: center;
  vertical-align: bottom;
  margin-top: 55px;
  font-family: OPPOSans;
}
.real-date {
  font-size: 25px;
  font-weight: 900;
  letter-spacing: 0px;
  line-height: 0px;
  color: rgba(0, 0, 0, 1);
  text-align: center;
  vertical-align: bottom;
  margin-top: 55px;
  font-family: OPPOSans;
}
.real-week-info {
  margin-top: 30px !important;
  margin: 0 auto;
  width: 59%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-size: 23px;
  font-weight: 900;
  letter-spacing: 0px;
  line-height: 0px;
  color: rgba(0, 0, 0, 1);
  text-align: center;
  vertical-align: bottom;
  font-family: OPPOSans;
}
</style>
