<template>
  <div class="new-task">
      <input type="text" v-model="name" @keydown.enter="add"
         class='form-element' placeholder='Nova tarefa?'>
      <button class='form-element' @click="add">+</button>
  </div>
</template>

<script>
export default {
   data() {
      return {
         name: ''
      }
   },
   methods: {
      add() {
         this.$emit('taskAdded', {name: this.name})
         this.name = ''
      }
   }
}
</script>

<style>
   .new-task {
      margin: 35px 0;
      width: 100%;
      display: flex;
      justify-content: center;
   }

   .form-element {
      outline: none;
      font-size: 1.5rem;
      border: 1px solid #fff;
      padding: 5px 10px 8px;
      color: #fff;
   }
   input.form-element {
      width: 422px;
      background: #fff2;
      border-top-left-radius: 8px;
      border-bottom-left-radius: 8px;
   }
   button.form-element {
      border-left: none;
      background: rgb(52, 197, 255);
      border-top-right-radius: 8px;
      border-bottom-right-radius: 8px;
   }

   @media (max-width: 600px) {
      input.form-element {
         width: 75%;
      }
      .new-task {
         margin: 15px 0;
      }
   }
</style>