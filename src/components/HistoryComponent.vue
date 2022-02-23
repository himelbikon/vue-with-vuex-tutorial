<template>
  <div>
    <h4 class="container">History</h4>
    <div class="flex">
      <p
        v-for="(number, index) in history"
        :key="index"
        :class="activeIndexes(value).includes(index) && 'bold'"
      >
        <!-- :class="activeIndexes(parseInt(value)).includes(index) && 'bold" -->
        {{ number }}
      </p>
    </div>
    <input
      type="number"
      placeholder="Search By Index"
      v-model="value"
      name=""
      id=""
    />
  </div>
</template>

<script>
import { mapState, mapGetters } from "vuex"

export default {
  data() {
    return {
      value: 0,
    }
  },
  computed: {
    ...mapState(["history"]),
    ...mapGetters(["activeIndexes"]),
  },
}
</script>

<style>
.container {
  margin-top: 7rem;
}
.flex {
  display: flex;
  margin: 0 auto;
  justify-content: center;
  text-align: center;
  width: 25rem;
  flex-wrap: wrap;
}

.flex p {
  margin: 1rem;
}

.bold {
  font-weight: 900;
}
</style>
