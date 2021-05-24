<template>
  <div>
    Images Comp
    <div class="container bg-success rounded">
      <div class="row d-flex">
        <div class="col" v-for="(img, i) in obj" :key="i">
          <img
            style="max-height: 200px; max-width: 300px"
            :src="'/images/' + i + '.jpg'"
            alt=""
            class="img-fluid rounded mx-auto d-block"
          />
          <button class="btn btn-danger btn-rounded" style="position: absolut">
            save
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import json from "../assets/data.json";
export default {
  data() {
    return {
      obj: {},
      src: "",
    };
  },

  filters: {
    filterimage(e) {
      return (e = e.replace(/[^0-9]+/g, ""));
    },
  },

  mounted() {
    this.obj = json;
  },
};
</script>

<style>
</style>