<template>
  <q-page>
    <div class="center-items">
      <img src="https://i.pinimg.com/originals/63/eb/cb/63ebcb2e3ca90717c34470e7407b00c4.jpg" width="300" >
      <h3>mi primer app con quasar</h3>
      <p>compilada con capacitor para android</p>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
});
</script>

<style scoped>
.center-items{
  display: grid;
  place-content: center;
  text-align: center;
}
</style>
