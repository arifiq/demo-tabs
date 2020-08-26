<template>
<div class="content">
    <div class="sect">
        <image class="image" :src="url"></image>
    </div>
    <div class="sect">
        <text>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sit illo
            perferendis fugiat nobis enim iure dolor beatae ducimus reprehenderit et
            harum consectetur culpa sint nostrum officia, quam distinctio maxime non.
        </text>
    </div>
</div>
</template>
<script>
/* eslint-disable */
export default {
    data() {
        return {
            url : './images/flower1.jpg'
        }
    }
}
</script>
<style scoped>
.content {
    margin: 5px;
    text-align: start;
    display: flex;
    flex-direction: row;
}
.sect {
    flex: 1;
}
.image{
    width: 100px;
    height: 100px;
}
</style>
