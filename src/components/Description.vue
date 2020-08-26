<template>
<div class="content">
    <div class="sect-img">
        <image class="image" :src="url"></image>
    </div>
    <div class="sect-desc">
        <text>Lorem ipsum, dolor sit amet consectetur adipisicing elit.Sit illoperferendis fugiat nobis enim iure dolor beatae ducimus reprehenderit et harum consectetur culpa sint nostrum officia, quam distinctio maxime non.</text>
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
    height: 100%;
    border: none;
}
.sect-img {
    flex: 1;
}
.sect-desc {
    flex: 4;
}
.image{
    width: 100px;
    height: 200px;
}
</style>
