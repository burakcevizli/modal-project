<template>
  <h1>{{ title }}</h1>
  <MyModal />
</template>

<script>
import MyModal from "./components/MyModal.vue";


export default {
  name: "App",
  components: { MyModal },
  data() {
    return {
      title: "My First Vue App",
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
  },
};
</script>