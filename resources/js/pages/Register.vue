<template>
    <layout>
        <div style="margin-top: 80px">

            <div v-for="(error, index) in errors" :key="index" style="border: 1px solid red; margin-bottom: 10px">
                {{ error }}
            </div>


            <form @submit.prevent="handleForm">
                <input type="text" placeholder="seu nome" v-model="form.name"/>
                <input type="email" placeholder="seu email" v-model="form.email"/>
                <input type="password" placeholder="sua senha" v-model="form.password"/>
                <button type="submit">Cadastrar</button>
            </form>
        </div>
    </layout>
</template>

<script>
import Layout from '../Layout.vue'
export default {
    props: {
        errors: Object,
    },
    components: { Layout },
    data: () => {
        return {
            form: {
                name: null,
                email: null,
                password: null,
            }
        }
    },
    methods: {
        handleForm() {
            this.$inertia.post('/register', this.form);
        }
    }

}
</script>


<style>

</style>