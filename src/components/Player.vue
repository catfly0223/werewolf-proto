<template>
  <button>
        {{ name }}
        {{ role }}
        {{ status }}
  </button>
</template>

<script>
export default {
    name: "Player",
    props: {
        id: String,
        name: String,
        role: String,
        status: String,
    }
}
</script>

<style>

</style>