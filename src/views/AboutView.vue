<template>
  <div class="about">
    <div class="range">
      <el-date-picker v-model="showTabTime1" type="datetimerange" valueFormat="yyyy-MM-dd HH:mm:ss"
        start-placeholder="开始日期" end-placeholder="结束日期">
      </el-date-picker>
    </div>
    <div class="range">
      <el-date-picker v-model="showTabTime2" type="datetimerange" valueFormat="yyyy-MM-dd HH:mm:ss"
        start-placeholder="开始日期" end-placeholder="结束日期">
      </el-date-picker>
    </div>
    <div class="ww">
      <div class="box">大大</div>
      <div class="box">小小</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showTabTime1: '',
      showTabTime2: '2020-12-12 12:00:00',
    }
  },
}
</script>
<style lang='scss' scoped>
.about {
  ::v-deep .el-range-input::placeholder {
    color: #333;
  }

  .box {
    font-size: 20px;
  }

  .ww .box:first-of-type {
    color: red;
  }
}
</style>
