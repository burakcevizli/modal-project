<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <teleport to=".modals" v-if="showModal">
    <MyModal :header="header" :text="text" theme="sale" @close="openModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">More Info</a>
      </template>
      <h1>Ninja GateAWAY</h1>
      <P>gRAB YOR NINJAAAAAA</P>
    </MyModal>
  </teleport>
  <div v-if="showModalTwo">
    <MyModal @close="openModalTwo">
      <h1>Sign up to newletter</h1>
      <P>gRAB YOR NINJAAAAAA22222222</P>
    </MyModal>
  </div>
  <button @click="openModal">Open Modal</button>
  <button @click="openModalTwo">Open ModalTwo</button>
</template>

<script>
import MyModal from "./components/MyModal.vue";

export default {
  name: "App",
  components: { MyModal },
  data() {
    return {
      title: "My First Vue App",
      showModal: false,
      showModalTwo: false,
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
    openModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>
