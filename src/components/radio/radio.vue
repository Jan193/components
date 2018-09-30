<style lang='scss'>
.radio {
    display: inline-block;
    border: 1px solid #bbb;
    border-radius: 50%;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: -2;
    transition: 1s;
    background-color: blue;
    width: 80%;
    height: 80%;
}
input[type="radio"] {
    position: absolute;
    left: 0;
    top: 0;
    z-index: 1;
    opacity: 0;
    margin: 0;
    background-color: transparent;
}
.radio-box {
  position: relative;
  display: inline-block;
  border-radius: 50%;
  border: 1px solid #bbb;
  overflow: hidden;
  // box-sizing: border-box;
  width: 16px;
  height: 16px;
  text-align: center;
  padding: 4px;
}
.radio--active {
  border-color: blue;
}
</style>
<template>
  <div class=''>
    <span class="radio-box" @click="getStatus($event)" :class="radioVal === 'male' ? 'radio--active' : ''">
      <input type="radio" name="sex" value="male" class="sex">
      <span class="radio" v-show="radioVal === 'male'"></span>
    </span>
    <span class="radio-box" @click="getStatus" :class="radioVal === 'female' ? 'radio--active' : ''">
      <input type="radio" name="sex" value="female" class="sex">
      <span class="radio" v-show="radioVal === 'female'"></span>
    </span>

    <!-- <button @click="getStatus()">get status</button> -->
  </div>
</template>

<script>

export default {
  data() {
    return {
      radioVal: '',
    }
  },
  components: {
  },
  mounted() {
    this.$nextTick(function () {

    })
  },
  methods: {
    getStatus() {
      let sexs = document.getElementsByClassName('sex');
      sexs = [...sexs]
      sexs.map(item => {
        if (item.checked) {
          this.radioVal = item.value;
        }
      })
    },
  }
}

</script>

