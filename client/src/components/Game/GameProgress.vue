<template>
  <div>
    <h2 class="loadingText">Game time left</h2>
    <div class="progressBar">
      <i class="loading-icon fas fa-compact-disc"></i>
    </div>
  </div>
</template>

<script>
// This page simply collects various data through props and displays them for the user, no functionality

export default {
  data: function() {
    return {
      song: ""
    };
  },
  props: ["name"]
};
</script>

<style scoped>
.progressBar {
  height: 3.2rem;
  background-color: white;
  border-radius: 0px 65px 65px 0px;
  width: 100%;
  animation: progressBar 300s 1 linear;
  transition: 1s;
}

.loading-icon {
  float: right;
  font-size: 3rem;
  color: #ed4c67;
  animation-name: rotate;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
  display: inline-block;
  margin-right: 0.5rem;
  margin-top: 0.1rem;
}

.loadingText {
  color: white;
  font-weight: 200;
  margin-bottom: 0;
  text-transform: uppercase;
}

@keyframes progressBar {
  0% {
    width: 100%;
  }
  100% {
    width: 0%;
  }
}
</style>
