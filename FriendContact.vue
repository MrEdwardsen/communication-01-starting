<template>
  <li>
    <h2>{{ name }} <span v-if="isMyFavorite">**Favorite**</span></h2>
    <button @click="toggleDetails">Details</button>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <ul v-if="detailsAreVisible">
      <li>
        <strong>Phone:</strong>
        {{ phoneNumber }}
      </li>
      <li>
        <strong>Email:</strong>
        {{ emailAddress }}
      </li>
      <li>
        <strong>Wohnort:</strong>
        {{ zuhause }}
      </li>
    </ul>
  </li>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    phoneNumber: {
      type: String,
      required: true
    },
    emailAddress: {
      type: String,
      required: true
    },
    zuhause: {
      type: String,
      required: true
    },
    isFavorite: {
      type: Boolean,
      required: false,
      default: false,
    }
  },
  data() {
    return {
      detailsAreVisible: false,
      isMyFavorite: this.isFavorite,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
      console.log(this.phoneNumber);
    },
    toggleFavorite() {
      this.isMyFavorite = !this.isMyFavorite;
    }
  }
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}
html {
  font-family: "Jost", sans-serif;
}
body {
  margin: 0;
}
header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #e28c0b;
  color: #2bff00;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
ul {
  margin: 0;
  padding: 0;
  list-style: none;
}
li {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}
h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #000;
  margin: 0 0 1rem 0;
}
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #fffb00;
  background-color: #fffb00;
  color: #e100ff;
  padding: 0.05rem 1rem;
  margin-left: 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
button:hover,
button:active {
  background-color: #0059ff;
  border-color: #0059ff;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>
