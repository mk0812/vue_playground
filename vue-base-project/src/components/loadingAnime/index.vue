<script>
import axios from 'axios'
import Loading from '@/components/loadingAnime/loading.vue'
export default {
    components: {
        Loading
    },
    data() {
        return {
            height: 0,
            list : []
        }
    },
    watch: {
        list: () => {
            this.$nextTick(() => {
                this.height = this.$refs.body.getBoundingClientRect().height
            })
        }
    },
    methods: {
        loadContent() {
            this.list = []
            axios.get('/data/data.json').then(response => {
                setTimeout(() => {
                    this.list = response.data
                },1500)
            })
        }
    },
    created() {
        this.loadContent()
    },
}
</script>