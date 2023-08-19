<template>
  <ul class="move_list">
    <MoveItem v-for="movie in movies" :key="movie.id" :movie="movie"
     @onClick="$emit('onClick', $event)"
     @onRemove="$emit('onRemove',$event)"
     />
  </ul>

</template>

<script>
import MoveItem from "@/components/MoveItem.vue"
export default{
    name: "MoveList",
    components: {
        MoveItem,
    },
   props: {
    movies: {
        type: Object,
        required: true
    }
   }
}
</script>

<style lang="scss" scoped>
.move_list {
    margin-top: 2rem;
    padding: 25px;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px  rgba($color: #8a878713, $alpha: 1.0);
}
</style>