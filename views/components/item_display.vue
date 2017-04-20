<!-- TODO: Hãy viết thành một component hoàn chỉnh -->
<template lang="html">
    <div v-for="item in images">
        <img  :src="'/public/image/' + item.photo" :alt="item.name" width="128" height="128">
    </div>
</template>

<script>
export default {
    props: ['things']
}
</script>

<style lang="css">
</style>