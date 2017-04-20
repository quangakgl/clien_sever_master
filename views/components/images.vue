<template lang="html">
    <div>
        <div v-for="item in images" class="col-md-3">
            <img :src="'/public/image/' + item.photo" :alt="item.name" width="100%" height="auto"  style="border: 1px solid">
            <p class="text-center" style="font-size: 20px;border: 1px solid ">{{item.name}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: ['images']
}
</script>

<style lang="css">

</style>