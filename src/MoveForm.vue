<template>
  <div class="move_form">
    <h3 class="move_form-title">Yangi kino qo'shish</h3>
    <form action="" class="move_form-add" @submit.prevent>
        <input type="text" class="move_form-input" placeholder="Qanday kino ?..." :value="name" @input="name=$event.target.value" required>
        <input required type="number" class="move_form-input" placeholder="Necha marotaba ko'rilgan ?..." :value="viwers" @input="viwers= $event.target.value">
        <button class="move_form-btn" type="submit" @click="addMove">Qo'shish</button>
    </form>
  </div>
</template>

<script>
export default {
    name: "MoveFrom",
    data () {
        return {
            name: "",
            viwers: ""
        }
    },
    methods: {
        addMove() {
            if(!this.name || !this.viwers) return
            const newMove = {
                name: this.name,
                viwers: this.viwers,
                like: false,
                color: false,
                id: Date.now()
            }
        this.$emit('createMove',newMove)
        this.name = ""
        this.viwers = ""
        
    }
    }

}
</script>

<style lang="scss" scoped>
.move_form {
    margin-top: 2rem;
    padding: 25px;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px  rgba($color: #8a878713, $alpha: 1.0);
    display: flex;
    flex-direction: column;
    gap: 20px;
   &-input {
    padding: 10px 0 10px 20px;
    width: 42%;
   }
    &-btn {
        padding: 10px 20px 10px 20px;
        text-align: start;
        background: #fff;
        border: 1px solid black;
        transition: 0.5s;
        font-size: 16px;
        letter-spacing: 2px;
        border-radius: 5px;
    }
    &-btn:hover {
        background: black;
        color: #ffff;
    }
}


</style>