<template>
  <div class="info">
    <h1 class="info_title">BARCHA KINOLAR SONI: {{ info }} </h1>
    <h1 class="info_titl">SEVIMLI KINOLAR: {{like}}</h1>
  </div>
</template>

<script>
export default {
  name: "Info",
  props: {
    info: {
      type: Number,
      required: true
    },
    like: {
      type: Number,
      required: true
    }
  } 
}
</script>

<style lang="scss" scoped>

.info {
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin-top: 2rem;
    padding: 1.5rem;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px  rgba($color: #8a878713, $alpha: 1.0);
    padding: 25px;
}

</style>