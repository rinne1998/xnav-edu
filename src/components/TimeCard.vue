<template>
  <div class="TimeCard">
    <div class="real-time">{{ realTime }}</div>
    <div class="real-date">{{ realDate }}</div>
    <div class="real-week-info">
      <div class="real-week">{{ realWeek }}</div>
      <div class="real-week-of-year">{{ realWeekOfYear }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TimeCard",
  data() {
    return {
      realTime: "19:19:10",
      realDate: "2022年11月11日",
      realWeek: "周",
      realWeekOfYear: "第37周",
    };
  },
  mounted() {
    this.setTime();
    if (this.timer) {
      clearInterval(this.timer);
    } else {
      this.timer = setInterval(this.setTime, 1000);
    }
  },
  beforeDestroy() {
    clearInterval(this.timer);
  },
  methods: {
    setTime: function () {
      var temp = this.getDate();
      this.realTime =
        (temp.hour < 10 ? "0" : "") +
        temp.hour +
        ":" +
        (temp.minute < 10 ? "0" : "") +
        temp.minute +
        ":" +
        (temp.second < 10 ? "0" : "") +
        temp.second;
      this.realDate = temp.year + "年" + temp.month + "月" + temp.dates + "日";
      this.realWeek = temp.week;
      this.realWeekOfYear = "第" + temp.weeks + "周";
    },
    getDate: function () {
      var date = new Date();
      var year = date.getFullYear(); //  返回的是年份
      var month = date.getMonth() + 1; //  返回的月份上个月的月份，记得+1才是当月
      var dates = date.getDate(); //  返回的是几号
      var day = date.getDay();
      var hour = date.getHours();
      var minute = date.getMinutes();
      var second = date.getSeconds();
      var arr = ["周日", "周一", "周二", "周三", "周四", "周五", "周六"];
      var week = arr[day];
      var endDate = new Date(),
        curYear = endDate.getFullYear(),
        startDate = new Date(curYear, 0, 1);

      var startWeek = startDate.getDay(), // 1月1号是星期几:0-6
        offsetWeek = 0; //用来计算不完整的第一周，如果1月1号为星期一则为0，否则为1

      if (startWeek != 1) {
        offsetWeek = 1;
        if (!startWeek) {
          startDate.setDate(1);
        } else {
          startDate.setDate(8 - startWeek); // (7 - startWeek + 1)
        }
      }
      var distanceTimestamp = endDate - startDate,
        days = Math.ceil(distanceTimestamp / (24 * 60 * 60 * 1000)) + startWeek,
        weeks = Math.ceil(days / 7) + offsetWeek;
      return {
        year,
        month,
        dates,
        week,
        hour,
        minute,
        second,
        weeks
      };
    },
  },
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
  letter-spacing: 0px;
  text-align: justify;
}
.real-time {
  font-size: 60px;
  font-weight: 900;
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
  line-height: 0px;
  color: rgba(0, 0, 0, 1);
  text-align: center;
  vertical-align: bottom;
  font-family: OPPOSans;
}
</style>
