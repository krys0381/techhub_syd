<template>
  <div class="card card-body mt-4">
    <!-- using @submit as a click function - add prevent to stop from refreshing page -->
    <form @submit.prevent="onSubmit">
          
      <div class="form-group">
        <label>Date</label>
        <input 
          type="text"
          class="form-control"
          v-model="form.date"
          required
        />
      </div>
      
      <div class="form-group mt-3">
        <label>Name</label>
        <input 
          type="text" 
          v-model="form.name" 
          class="form-control" 
          required 
        />
      </div>

      <div class="form-group mt-3">
        <label>Description</label>
        <input 
          type="text"
          class="form-control"
          v-model="form.description"
          required
        />
      </div>

      <div class="form-group mt-3">
        <label>Location</label>
        <input 
          type="text"
          class="form-control"
          v-model="form.location"
          required
        />
      </div>

      <div class="form-group mt-3">
        <label>Time</label>
        <input 
          type="text"
          class="form-control"
          v-model="form.time"
          required
        />
      </div>

      <button type="submit" class="btn btn-success mt-3">
        Create Event
      </button>
    </form>
  </div>
</template>

<script>
import { reactive } from 'vue'
import { createEvent } from '../../firebase.js' // maybe this make error

  export default {
   setup() {
     const form = reactive({
       date: '',
       name: '',
       description: '',
       location: '',
       time: '',
     })

     const onSubmit = async () => {
       // spread operator to add field + invoking our createProject function from firebase.js
       await createEvent({ ...form }) 
       // after create - empty input field
       form.date = ''
       form.name = ''
       form.description = ''
       form.location = ''
       form.time = ''
     }

     return { form, onSubmit }
   } 
  }
</script>

<style lang="scss" scoped>

</style>