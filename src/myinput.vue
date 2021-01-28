<template>
    <div>
        <input v-model="value">
    </div>
</template>

<script>
export default {
    data(){
        return{
            value:''
        }
    },
    methods:{
        onInput(e){
            const v = e.target.value
            this.$emit('input',v)
        }
    }
}
</script>