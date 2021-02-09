<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        {{ customers }}
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        name: 'HelloWorld',
        props: {
            msg: String
        },
        created() {
            axios.get(this.custURL)
              .then(r => {
                console.log(r)
              })
              .catch(e => {
                console.log(e)
              })
        },
        data() {
            return {
                custURL: 'http://localhost:3000/Customers',
                customers: []
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
