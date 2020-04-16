<template>
  <div class="task" :class="stateClass">
     <span class="close" @click="$emit('taskDeleted')">X</span>
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
   position: relative;
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

.pending .close {
   background-color: #b73229;
}
.done .close {
   background-color: #0a8f09;
}
.close {
   position: absolute;
   right: 5px;
   top: 5px;
   font-size: 0.7rem;
   font-weight: 600;
   width: 18px;
   height: 15px;
   border-radius: 50%;
   display: flex;
   justify-content: center;
   align-items: top;
}
</style>