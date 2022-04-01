<template>
  <div>
    <h3 :class="['alert',color]">

      <input type="text" class="form-control" v-model="message" @keyup.enter="edit" v-if="isEdit">

      <span @dblclick="edit" v-else>
        {{message}}
      </span>

      <div  v-if="isLoading" class="spinner-border text-info" role="status">
        <span class="visually-hidden">Loading...</span>
      </div>
    </h3>
  </div>
</template>

<script>
export default {
  name : "Alert",
  props: {
    message: {
      type: String,
      default: 'Say Something'
    },
    color : {
      type : String,
      default: 'alert-info'
    }
  },

  data() {
    return {
      isLoading: false,
      isEdit : false
    }
  },
  methods: {
    edit() {
      this.isEdit = !this.isEdit
    }
  },

}
</script>

<style scoped>

</style>