<template>
  <div class="sorch">
    <input type="text" class="sorch_input" placeholder="Kinolarni qidirish" :value="term" @input="onTarget">
    <div class="sorch_btn">
      <Button text="Barch kinolar" />
      <Button text="Mashxur kinolar" />
      <Button text="Eng ko'p ko'rilgan kinolar" />
    </div>
  </div>
</template>

<script>
import Button from "@/components/Button.vue"
export default {
  name: "Sorch",
  components: {
    Button,
  },
  props: {
    onUpdate: {
      type: Function,
      required: true
    }
  },
  data() {
    return {
      term: ""
    }
  },
  methods: {
    onTarget(e) {
      this.term = e.target.value
      let tem = this.term.toLowerCase()
      this.onUpdate(tem)
    }
  }
}


</script>

<style lang="scss" scoped>
.sorch {
    margin-top: 2rem;
    padding: 25px;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px  rgba($color: #8a878713, $alpha: 1.0);
    display: flex;
    flex-direction: column;
    gap: 20px;
    &_input {
        height: 60px;
        padding: 0 15px;
        font-size: 22px;
        border: 3px solid #2057a54b;
        border-radius: 10px;
       
    }
    &_btn {
      display: flex;
    }
}
</style>