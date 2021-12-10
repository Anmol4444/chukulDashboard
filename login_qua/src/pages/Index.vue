<template>
  <!-- <q-page class="flex flex-center">
    <img
      alt="Quasar logo"
     
      style="width: 200px; height: 200px"
    >
  </q-page> -->
  <UserForm />
</template>

<script>
import { defineComponent } from 'vue';
import UserForm from '../components/UserForm.vue';

export default defineComponent({
    name: "PageIndex",
    components: { UserForm }
})
</script>
