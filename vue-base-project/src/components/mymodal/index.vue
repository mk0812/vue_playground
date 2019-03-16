<template>
    <div class="example-modal-window">
        <p>modalWindow open</p>
        <button @click="openModal">open</button>

        <!-- ModalWindow Component define -->
        <MyModal></MyModal>
    </div>
</template>

<script>
import MyModal from 'MyModal.vue'
export default {
    components: {
        MyModal
    },
    data() {
        return {
            modal: false,
            message: ''
        }
    },
    methods: {
        openModal: () => {
            this.modal = true
        },
        closeModal: () => {
            this.modal = false
        },
    },
}
</script>