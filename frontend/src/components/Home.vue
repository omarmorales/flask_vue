<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'Home',
    data () {
        return {
        msg: 'Bienvenido a tu Vue.js App'
        }
    },
    methods: {
        getMsg () {
            const path = 'http://localhost:5000/api/v1.0/mensaje'

            axios.get(path).then((res) => {
                this.msg = res.data
            })
            .catch((err) => {
                console.log(err);
            })
        }
    },
    created() {
        this.getMsg();
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>