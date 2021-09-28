<template>
  <div>
      {{emailIndex + 1}} - {{ emailText }}
  </div>
</template>

<script>
export default {
    props: {
        emailText: String,
        emailIndex: Number,
    }
}
</script>

<style lang="scss">
div{
    font-size: 1.5rem;
    padding: 15px;
}
</style>