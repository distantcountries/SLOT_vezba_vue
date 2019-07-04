<template>
    <div>
        <div>
            <slot name="title"></slot>
            <p>I am the child Component</p>
            <slot name="content"></slot>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {

        }
    }
}
</script>

<style>

</style>
