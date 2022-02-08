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
    <div class="panel">
      <div class="sector">
        <div class="sector-inner">
          <span>谢谢参与</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span> 50 积分</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span>谢谢参与</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span>100话费</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span> 50 积分</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span>谢谢参与</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span>100话费</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span>谢谢参与</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span> 50 积分</span>
        </div>
      </div>
      <div class="sector">
        <div class="sector-inner">
          <span>10元话费</span>
        </div>
      </div>
      <div class="pointer">开始抽奖</div>
    </div>
  </div>

</template>
<script>
export default {
  name: "Turntable",
  data() {
    return {
      dataBase: []
    }
  }
}
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
  height: 200px;
  width: 200px;
  padding: 20px;
  margin: 20px;
  background-color: #c0381f;
  box-shadow: #000000 0px 0px 10px;
  border-radius: 50%;
}
.light {
  position: absolute;
  height: 10px;
  width: 10px;
  border-radius: 50%;
  top: 5px;
  left: 115px;
  transform-origin: 5px 115px;
}
.light:nth-child(2n) {
  background-color: #fafce7;
}
.light:nth-child(2n + 1) {
  background-color: #ffe58b;
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
  height: 200px;
  width: 200px;
  background-color: #b7b7b7;
  border-radius: 100px;
}
.sector {
  position: absolute;
  width: 100px;
  height: 200px;
  border-radius: 0px 100px 100px 0;
  overflow: hidden;
  left: 100px;
  top: 0px;
  transform-origin: left center;
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
.sector-inner {
  text-align: center;
  display: block;
  width: 40px;
  padding: 5px 3px 0 57px;
  height: 195px;
  transform: translateX(-100px) rotate(36deg);
  transform-origin: right center;
  border-radius: 100px 0 0 100px;
}
.sector-inner span {
  display: block;
  transform-origin: center;
  transform: rotate(-19deg);
  color: #d46854;
}
.pointer {
  position: absolute;
  left: 79px;
  top: 79px;
  z-index: 10;
  height: 30px;
  width: 30px;
  padding: 6px;
  color: #fff899;
  line-height: 15px;
  font-size: 12px;
  text-align: center;
  background-color: #dc5b5b;
  border-radius: 50%;
  border: 1px solid #c0381f;
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
</style>
