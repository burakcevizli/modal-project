<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <MyModal :header="header" :text="text" theme="sale" @close="openModal" >
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Ninja GateAWAY</h1>
      <P>gRAB YOR NINJAAAAAA</P>
    </MyModal> 
  </div>
  <button @click="openModal">Open Modal</button>
</template>

<script>
import MyModal from "./components/MyModal.vue";

export default {
  name: "App",
  components: { MyModal },
  data() {
    return {
      title: "My First Vue App",
      header: "Sign up for the Giveaway!",
      text: "Grab your ninja swag for half price",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    openModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>
