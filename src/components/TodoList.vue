<template>
    <div>
        <div>
            <slot name="title"></slot>
            <p>I am the child Component</p>
            <slot v-if="shouldShowContent" name="content"></slot>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        shouldShowContent: {
            type:Boolean,
            default:false
        }
    },

    data(){
        return {
            
        }
    }
}
</script>

<style>

</style>
