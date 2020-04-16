<template>
  <div class="tasks-progress">
     <span class="progress-value">{{ progress }}%</span>
     <div class="progress-bar" :style="{width: progress + '%'}"></div>
  </div>
</template>

<script>
export default {
   props: {
      progress: {type: Number, default: 0}
   }
}
</script>

<style>
   .tasks-progress {
      position: relative;
      width: 500px;
      height: 20px;
      border: 2px solid #fff5;
      border-radius: 10px;
   }
   .progress-value {
      position: absolute;
      left: 50%;
   }
   .progress-bar {
      background-color: green;
      height: 20px;
      transition: .5s cubic-bezier(0.075, 0.82, 0.165, 1);
   }
</style>