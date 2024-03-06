<template>
  <h1>{{ title }}</h1>
  <Modal @close="handleClick" v-if="showFirstModal">
    <template v-slot:firstModal>
      <h1>Mega Giveaway</h1>
      <p>Grab your swag gifts</p>
    </template>
  </Modal>
  <Modal v-if="showSecondModal" @close="secondHandleClick">
    <template v-slot:secondModal>
      <h1 class="modal">Gifts for Everyone</h1>
      <p>Win some exciting prizes</p>
    </template>
  </Modal>
  <div class="buttons">
    <button @click="handleClick">{{ firstButtonText }}</button>
    <button @click="secondHandleClick">{{ secondButtonText }}</button>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data: () => ({
    showFirstModal: false,
    showSecondModal: false,
    firstButtonText: "Show First Modal",
    secondButtonText: "Show Second Modal",
  }),
  methods: {
    handleClick() {
      this.showFirstModal = !this.showFirstModal;

      // this.title = "Hello World";
      // console.log(this.$refs.name.value);
      // this.$refs.name.classList.add("active");
      // this.$refs.name.focus();
    },
    secondHandleClick() {
      this.showSecondModal = !this.showSecondModal;
    },
    // handleClose() {
    //   this.showModal = false;
    // },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.buttons {
  display: flex;
  justify-content: space-around;
  margin-top: 20px;
}
button {
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
</style>
