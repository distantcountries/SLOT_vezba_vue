<template>
    <div>
        <div v-for="(user, index) in users" :key="index">
            <slot :user="user">
                {{ user.name }}
            </slot>
        </div>
    </div>
</template>

<script>
export default {

    data(){
        return {
            users: [
                        { name:'Misa', isGoingToExit: true },
                        { name:'Pera', isGoingToExit: false },
                        { name:'Zika', isGoingToExit: true },
                        { name:'Mika', isGoingToExit: false },
                        { name:'Uros', isGoingToExit: false },
                        { name:'Srna', isGoingToExit: true },
                        { name:'Bora', isGoingToExit: false },
                        { name:'Laza', isGoingToExit: false },
                        { name:'Mira', isGoingToExit: true }
                    ]
            }
  },


}
</script>

<style>

</style>
