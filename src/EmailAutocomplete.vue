<template>
    <div>
        <input type="text" :list="componentId" :value="value" @input="updateValue($event)"
            :class="className" :placeholder="placeholder">
        <datalist :id="componentId">
            <option :value="getEmail(k, v)" v-for="(v, k) in suffixList"></option>
        </datalist>
    </div>
</template>

<script>
    export default {
        name: 'email-autocomplete',
        props: ['value', 'className', 'placeholder'],
        data() {
            return {
                componentId: '',
                suffixList: {
                    '@163.com': '',
                    '@126.com': '',
                    '@qq.com': '',
                    '@gmail.com': '',
                    '@sohu.com': '',
                    '@yahoo.com.cn': ''
                }
            }
        },
        methods: {
            updateValue(e) {
                this.$emit('input', e.target.value);
            },
            getEmail(suffix, origVal) {
                if (this.value.indexOf('@') >= 0) {
                    return origVal;
                } else {
                    let newValue = this.value + suffix;
                    this.suffixList[suffix] = newValue;
                    return newValue;
                }
            }
        },
        mounted() {
            this.componentId = 'email-autocomplete-' + new Date().getTime();
        }
    }
</script>

<style>
    
</style>