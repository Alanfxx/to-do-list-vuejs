<template>
  <div class="task" :class="stateClass">
     <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
   props: {
      task: { type: Object, required: true }
   },
   computed: {
      stateClass() {
         return {
            pending: this.task.pending,
            done: !this.task.pending
         }
      }
   }
}
</script>

<style>
.task {
   box-sizing: border-box;
   width: 220px;
   height: 100px;
   border-radius: 8px;
   margin: 5px;
   padding: 10px;
   font-size: 1.2em;
   font-weight: 300;
   cursor: pointer;
   user-select: none;
   display: flex;
   justify-content: center;
   align-items: center;
}
.pending {
   background-color: #f44336;
   border-left: 12px solid #b73229;
}
.done {
   color: #DDD;
   background-color: #4caf50;
   border-left: 12px solid #0a8f09;
   text-decoration: line-through;
}
</style>