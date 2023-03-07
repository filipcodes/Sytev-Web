<template>
  <div
      class="grid-system-partners container-partners">
    <div v-for="partner in partners">
      <img
          class="image-partners"
          v-bind:src="'http://localhost:1337' + partner.attributes.image.data.attributes.url"
          alt="partner">
    </div>
  </div>
</template>

<script>
import axios from "axios";

const LOCALHOST_URL = "http://localhost:1337/";
export default {
  name: "partners",
  data() {
    return {
      partners: []
    }
  },
  mounted() {
    axios.get(LOCALHOST_URL + "api/partners?populate=image")
        .then(res => {
          this.partners = res.data.data
        })
        .catch(err => console.log(err));
  }
}
</script>

<style lang="scss" scoped>
.grid-system-partners {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 80px;
}

.container-partners {
  width: 100%;
  padding: 2rem;
  //overflow: hidden;
  margin: 5rem 0;
}

.image-partners {
  max-height: 100px;
}
</style>