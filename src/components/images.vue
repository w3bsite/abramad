<template>
  <div>
    Images Comp
    <div class="img-wrapper">
      <div class="container bg-success rounded">
        <div class="row d-flex">
          <div class="col" v-for="(img, i) in obj" :key="i">
            <img
              style="max-height: 200px; max-width: 300px"
              :src="'/images/img' + imageUrl + '.jpg'"
              alt=""
              class="img-fluid rounded mx-auto d-block"
            />
            <div class="img-overlay">
              <button class="btn btn-danger btn-rounded">save</button>
            </div>
          </div>
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
.container .btn {
  position: absolute;
  top: 10%;
  right: 5%;

  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);

  font-size: 10px;
}

.container .btn:hover {
  background-color: black;
}
</style>