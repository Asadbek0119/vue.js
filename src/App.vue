<template>
  <Info :info="movies.length" :like="movies.filter(c => c.like).length"/>
  <Sorch :onUpdate="onUbdate"/>
  <MoveList :movies="onSorch(movies,term)"
   @onClick="onClicks"
  @onRemove="onRemove"
  />
  <MoveForm @createMove="createMove"/>


</template>

<script>
import Info from "@/components/Info.vue";
import Sorch from "@/components/Sorch.vue";
import Button from "@/components/Button.vue"
import MoveList from "@/components/MoveList.vue"
import MoveForm from "@/MoveForm.vue"
export default {
  name:"App",
  components: {
  Info,
  Sorch,
  Button,
  MoveList,
  MoveForm
},
data () {
        return {
            movies: [
                {
                    name: "Omar",
                    viwers: 811,
                    color:false,
                    like: false,
                    id: 1
                },
                {
                    name: 'Empire of Osmon',
                    viwers: 411,
                    color: false,
                    like:false,
                    id: 2
                },
                {
                    name: "Ertuglul",
                    viwers: 711,
                    color: false,
                    like: false,
                    id: 3
                },
                {
                    name: "Ertuglul",
                    viwers: 711,
                    color: false,
                    like: false,
                    id: 4
                }
            ],
            term: ""
        }
    },
    methods: {
      createMove(item) {
        // console.log(item);
        this.movies.push(item)
      },
      onClicks({id,prop}) {
       
        this.movies = this.movies.map(item => {
          if(item.id == id) {
           return {...item, [prop] : !item[prop]}
            // console.log(item);
          }
          return item
        })
      },
      onRemove (id) {
        this.movies = this.movies.filter(c => c.id != id)
      },
      onSorch(arr,term) {
        if(term.length == 0) {
          return arr
        };
        return arr.filter(c => c.name.toLowerCase().indexOf(term) > -1)
      },
      onUbdate(term) {
        this.term = term
      }
    }
}
</script>

<style lang="scss" scoped>

</style>