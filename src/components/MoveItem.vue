<template>
  <div class="move_item" :class="[{like: movie.like}, {color: movie.color}]">
    <h4 class="move_item-title" @click="$emit('onClick',{id: movie.id, prop: 'like'})">{{movie.name}}</h4>
    <input type="text" class="move_item-input" :value="movie.viwers">
    <div class="move_item-icons">
        <button class="move_item-btn" @click="$emit('onClick',{id: movie.id , prop: 'color'})"><i class="fas fa-cookie"></i></button>
        <button class="move_item-btn" @click="$emit('onRemove',movie.id)"><i class="far fa-trash-alt"></i></button>
        <button class="move_item-btn"><i class="fas fa-star"></i></button>
    </div>
  </div>
</template>

<script>
export default {
    name: "MoveItem",
    props: {
        movie: {
            type: Object,
            required: true
        }
    },
    data () {
        return  {

        }
    }
}
</script>

<style lang="scss" scoped>
.move_item {
    width: 100%;
    padding: 15px;
    background: #fff;
    border-bottom: 2px solid #9d9494;
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    &-title {
        line-height: 35px;
        font-size: 20px;
        cursor: pointer;
        width: 550px;
    }
    &-input {
        line-height: 35px;
        font-size: 20px;
        border: 0;
        text-align: center;
        outline: none;
    }
    &-btn {
        width: 35px;
        height: 35px;
        margin: 3px;
        font-size: 17px;
        border: 0;
        cursor: pointer;
        background: #fff;
    }
    &-btn:nth-child(1) {
        color: #e09f3e;
    }
    &-btn:nth-child(2) {
        color: #e5383b;
    }
    &-btn:nth-child(3) {
        color: #ffd700;
        transition: 0.3s;
        transform: translateX(30px);
        opacity: 0;
    }
}
.move_item:last-child {
    border-bottom: none;
}
.move_item.like .move_item-btn:nth-child(3) {
    transform: translateX(-5px);
    opacity: 1;
}
.move_item.color .move_item-title {
    color: #e09f32;
}
.move_item.color .move_item-input {
    color: #e09f32;
}
</style>