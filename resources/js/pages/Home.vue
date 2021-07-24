<template>
    <layout>
        <div>Olá {{ user }} voce está na home.</div>
        <div v-if="$page.props.flash.success" style="border: 1px solid green;">
            {{ $page.props.flash.success }}
        </div>
    </layout>
</template>

<script>
import Layout from '../Layout.vue'
export default {
    props: {
        user: String,
        flash: {},
    },
    components: { Layout },
}
</script>

<style>

</style>