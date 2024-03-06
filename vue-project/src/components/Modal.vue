<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <slot name="firstModal"></slot>
      <slot name="secondModal"></slot>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: red;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
h1 {
  color: black;
  border: none;
  padding: 0px;
}
/* .modal.sale h1 {
  color: yellow;
} */
.modal p {
  font-style: normal;
}
.modal.sale {
  background: red;
}
.head {
  display: grid;
  justify-content: center;
  width: 100%;
  text-align: center;
}
.close {
  font-size: 30px;
  text-align: center;
  color: yellow;
  cursor: pointer;
}
.head h1 {
  color: white;
}
</style>
