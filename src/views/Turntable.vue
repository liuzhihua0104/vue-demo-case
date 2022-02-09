<template>
  <div class="wrapper">
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="light"></div>
    <div class="panel" :style="{ transform: `rotate(${deg}deg)` }">
      <div class="sector" v-for="(item, index) in data" :key="index">
        <!-- 			:style="{'transform':`rotate(${index*36-18})`}"
 -->
        <div class="sector-inner">
          <span>{{ item }}</span>
        </div>
      </div>
      <!-- <div class="sector">
				<div class="sector-inner"><span>50 积分</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>谢谢参与</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>100话费</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>50 积分</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>谢谢参与</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>100话费</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>谢谢参与</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>50 积分</span></div>
			</div>
			<div class="sector">
				<div class="sector-inner"><span>10元话费</span></div>
			</div> -->
      <div class="pointer" @click="play">开始抽奖</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Turntable",
  data() {
    return {
      data: [
        "谢谢参与",
        "50 积分",
        "谢谢参与",
        "100 积分",
        "谢谢参与",
        "150 积分",
        "谢谢参与",
        "500 积分",
        "600 积分",
        "700 积分",
      ],
      flag: false,
      timer: null,
      basic: 3600, //至少转几圈
      angle: 0, //目标角度
      deg: 0, // 转盘实时旋转的角度
    };
  },
  methods: {
    play() {
      if (this.flag) {
        return;
      }
	  this.timer=null;
	  this.angle=0;
	  this.deg=0;
	  console.log("return")
      let random = parseInt(Math.random() * 8);
      let obj = new Map();

      for (let i = 0; i < 10; i++) {
        obj.set(i, i * 36);
      }

      console.log(random, obj.get(random));
      this.angle = obj.get(random);
      this.run();

      //   (this.angle = random), obj.get(random);
    },

    run() {
      this.flag = true;
      let begin = 0;
      this.timer = setInterval(() => {
        if (Math.ceil(begin) >= this.basic + this.angle) {
          this.flag = false;
          clearInterval(this.timer);
          this.timer = null;
		
        }
        this.deg = Math.ceil(begin);
        // begin += 50;
		// 缓动公式：（目标值-当前值）*系数

		begin+=(this.basic+this.angle-begin)*0.1
      }, 50);
    },
  },
};
</script>
<style scoped lang="less">
/* 重置默认样式 */
* {
  margin: 0;
  padding: 0;
  border: none;
  outline: none;
}
.wrapper {
  position: relative;
  height: 500px;
  width: 500px;
  // padding: 20px;
  margin: 20px;
  // background-color: #c0381f;
  box-shadow: #000000 0px 0px 10px;
  border-radius: 50%;
  border: 20px solid yellow;
}
.light {
  position: absolute;
  height: 13px;
  width: 13px;
  border-radius: 50%;
  top: 70px;
  left: 50px;
  z-index: 999;
  transform-origin: 200px 180px;
}
.light:nth-child(2n) {
  // background-color: #fafce7;
  background: #000;
}
.light:nth-child(2n + 1) {
  background: red;
  // background-color: #ffe58b;
}
.light:nth-child(2) {
  transform: rotate(36deg);
}
.light:nth-child(3) {
  transform: rotate(72deg);
}
.light:nth-child(4) {
  transform: rotate(108deg);
}
.light:nth-child(5) {
  transform: rotate(144deg);
}
.light:nth-child(6) {
  transform: rotate(180deg);
}
.light:nth-child(7) {
  transform: rotate(216deg);
}
.light:nth-child(8) {
  transform: rotate(252deg);
}
.light:nth-child(9) {
  transform: rotate(288deg);
}
.light:nth-child(10) {
  transform: rotate(324deg);
}
.panel {
  position: relative;
  height: 500px;
  width: 500px;
  background-color: #b7b7b7;
  border-radius: 50%;
  .sector {
    position: absolute;
    width: 500px;
    height: 500px;
    border-radius: 0px 250px 250px 0;
    overflow: hidden;
    left: 250px;
    top: 0px;
    transform-origin: left center;

    .sector-inner {
      text-align: center;
      display: block;
      width: 40px;
      padding: 5px 3px 0 57px;
      height: 195px;
      transform: translateX(-100px) rotate(36deg);
      transform-origin: right center;
      border-radius: 250px 0 0 250px;
    }
    .sector-inner span {
      display: block;
      transform-origin: center;
      transform: rotate(-19deg);
      color: #d46854;
    }
  }

  .pointer {
    position: absolute;
    left: 250px;
    top: 250px;
    z-index: 10;
    height: 70px;
    width: 70px;
    padding: 6px;
    color: #fff899;
    line-height: 15px;
    font-size: 12px;
    text-align: center;
    background-color: #dc5b5b;
    border-radius: 50%;
    border: 1px solid #c0381f;
    transform: translate(-50%, -50%);
  }
  .pointer::after {
    content: "";
    position: absolute;
    left: 14px;
    top: -24px;
    border-width: 12px 6px;
    border-style: solid;
    border-color: transparent;
    border-bottom-color: #c0381f;
  }
}

.sector:nth-child(1) {
  transform: rotate(-18deg);
}
.sector:nth-child(2) {
  transform: rotate(18deg);
}
.sector:nth-child(3) {
  transform: rotate(54deg);
}
.sector:nth-child(4) {
  transform: rotate(90deg);
}
.sector:nth-child(5) {
  transform: rotate(126deg);
}
.sector:nth-child(6) {
  transform: rotate(162deg);
}
.sector:nth-child(7) {
  transform: rotate(198deg);
}
.sector:nth-child(8) {
  transform: rotate(234deg);
}
.sector:nth-child(9) {
  transform: rotate(270deg);
}
.sector:nth-child(10) {
  transform: rotate(306deg);
}
.sector:nth-child(2n + 1) .sector-inner {
  background: #fef6e0;
}
.sector:nth-child(2n) .sector-inner {
  background: #ffffff;
}
</style>
