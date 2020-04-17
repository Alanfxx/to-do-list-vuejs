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
      margin-top: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
   }
   .progress-value {
      position: absolute;
   }
   .progress-bar {
      background-color: green;
      height: 100%;
      border-radius: 5px;
      align-self: flex-start;
      transition: .5s cubic-bezier(0.075, 0.82, 0.165, 1);
   }
   @media (max-width: 600px) {
      .tasks-progress {
         width: 90%;
      }
      .tasks-progress {
         margin-top: 13px;
      }
   }
</style>