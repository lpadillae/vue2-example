<template>
  <div class="columns">
    <div class="column">
      <button type="button" @click="openModal">
        Abrir Modal
      </button>
    <modal-template v-if="showModal" @close="closeModal">
      <template slot="header">Manual Devices</template>
      <template slot="body">
        <imei-list-template></imei-list-template>
      </template>
    </modal-template>
    </div>
  </div>
</template>

<script>
import ModalTemplate from "./components/Modal.vue";
import ImeiListTemplate from "./components/ImeiList.vue"

export default {
  components: {
      ImeiListTemplate,
      ModalTemplate
  },
  name: 'app',
  data () {
    return {
      showModal: false
    }
  },
  methods: {
    openModal() {
      this.showModal = true
    },
    closeModal() {
      this.showModal = false
    }
  }
}
</script>
