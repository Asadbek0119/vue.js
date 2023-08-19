<template>
  <button class="btn">{{text}}</button>
</template>

<script>
export default {
name:"Button",
props: {
    text: {
        type: String
    }
}
}
</script>

<style lang="scss" scoped>
.btn {
    //width: 170px;
    padding: 10px 5px 10px 10px;
    text-align: start;
    background: #fff;
    border: 1px solid black;
    transition: 0.5s;
    font-size: 16px;
    letter-spacing: 2px;
    border-radius: 5px;
}
.btn:hover {
    background: black;
    color: #ffff;
}
</style>