<template>
  <h1>{{ title }}</h1>
  <MyModal :header="header" :text="text" theme="sale"/>
</template>

<script>
import MyModal from "./components/MyModal.vue";


export default {
  name: "App",
  components: { MyModal },
  data() {
    return {
      title: "My First Vue App",
      header:'Sign up for the Giveaway!',
      text:"Grab your ninja swag for half price"
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