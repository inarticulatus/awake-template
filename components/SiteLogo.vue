<template>
  <div style="top:20%;" class="logo-wrapper">
    <div>
     <img src="../assets/uploads/prakharphotologo.png">
    </div>
  </div>
</template>
<script>
export default {
  name: 'SiteLogo',
  data() {
    return {
      frames: 5,
      currentFrame: 1,
      blinking: true
    }
  },
  mounted() {
    setInterval(() => {
      const rand = Math.ceil(Math.random() * 10)
      this.blinking = rand % 2
    }, 1000)
  }
}
</script>
<style lang="scss">
@keyframes logoBlink {
  100% {
    transform: translateY(-360px);
  }
}
.logo-wrapper {
  position: relative;
  height: 50px;
  overflow: hidden;
  width: 200px;
  .logo-inner {
    position: absolute;
    height: 500px;
    img {
      display: block;
      height: 40px;
      margin: 5px;
      max-height: initial;
    }
    &.blink {
      animation: logoBlink 0.2s steps(8, end) alternate;
    }
  }
}
</style>
<style scoped>
p {
  font-size: 13pt;
}
</style>
