<template>
    <div class="example-modal-window">
        <p>modalWindow open</p>
        <button @click="openModal">open</button>

        <!-- ModalWindow Component define -->
        <MyModal v-if="modal" @close="closeModal">
            <p>Vue.js Modal Window!!</p>
            <div>
                <input type="text" v-model="message">
            </div>
            <!-- footerスロットコンテンツ -->
            <template slot="footer">
                <button @click="doSend">send</button>
            </template>
        </MyModal>
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
        doSend: () => {
            if(this.message.length > 0){
                alert(this.message)
                this.message = ''
                this.closeModal()
            }else{
                alert("message is not valid")
            }
        }
    },
}
</script>