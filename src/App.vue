<template>
    <div>
        <email-autocomplete v-model="email" class-name="email-input" placeholder="输入邮箱"></email-autocomplete>
        <div style="margin-top: 150px;">你输入的邮箱为：{{ email }}</div>
    </div>
</template>

<script>
    import EmailAutocomplete from './EmailAutocomplete.vue';

    export default {
        components: {
            EmailAutocomplete
        },
        data() {
            return {
                email: ''
            }
        }
    }
</script>

<style>
    .email-input {
        font-size: 14px;
        width: 200px;
        padding: 5px;
        outline: none;
        border: 1px solid #93c47d;
    }
</style>
