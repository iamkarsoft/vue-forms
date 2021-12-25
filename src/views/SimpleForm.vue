<template>
  <section>
    <h1 class="font-extrabold text-2xl block">Create an Event</h1>

    <form action="">
      <BaseSelect
      :options="categories"
      v-model="event.category"
      label="Select a category"
      />

      <h1  class="font-extrabold text-2xl block">Name & describe your event</h1>

        <BaseInput
         v-model="event.title"
         label="Title"
         type="text"/>

         <BaseInput
         v-model="event.description"
         label="Description"
         type="text"/>
        

   

      <h1 class="font-extrabold text-2xl block">Where is your event?</h1>
      <div class="form-group block mt-4">
        <label for="" class="font-bold text-xl block">location</label>
        <input type="text" name="" placeholder="location" v-model="event.location" id="" class="border border-gray-400 p-4 rounded-lg">
      </div>

      <div class="form-group block mt-4">
        <label for="" class="font-bold text-xl block">Are Pets Allowed?</label>
        <BaseRadio v-model="event.pets" :value="0" label="No" name="pets" />
        <BaseRadio v-model="event.pets" :value="1" label="Yes" name="pets" />
  
      </div>

      <div class="form-group block mt-4">
        <label for="" class="font-bold text-xl block">Extras</label>
       <BaseCheckbox type="checkbox" label="Catering" v-model="event.extras.catering" />
       <BaseCheckbox type="checkbox" label="Live Music" v-model="event.extras.music" />
      </div>
      <div class="form-group mt-4">
        <button>Submit</button>
      </div>
    </form>
  </section>
</template>


<script>

  import BaseInput from '../components/BaseInput.vue'
  import BaseRadio from '../components/BaseRadio.vue'
  import BaseSelect from '../components/BaseSelect.vue'
  import BaseCheckbox from '../components/BaseCheckbox.vue'
  export default{
      components:{
        BaseInput,
        BaseSelect,
        BaseCheckbox,
        BaseRadio
      },
      data() {
        return {
          categories: [
            'food',
            'community',
            'nature'
          ],
            event:{
              description: '',
              category: '',
              pets: 1,
              extras: {
                catering: false,
                music: false,
              },
              location: '',
              title:''
            }
        }
      }
  }
</script>