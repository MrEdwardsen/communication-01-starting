<template>
  <section>
    <header>
      <h1>My Friends</h1>
    </header>
    <new-friend></new-friend>
    <ul>
      <friend-contact
        name="Max Muster"
        phone-number="0123 456 789"
        email-address="manuel@test.com"
        zuhause="Knechtstraße 1"
      ></friend-contact>
      <friend-contact
        name="Johannes Wegeler"
        phone-number="4567 890 123"
        email-address="julie@test.com"
        zuhause="Steinacker 6"
      ></friend-contact>
      <friend-contact
        name="Julia Roberts"
        phone-number="3456 789 312"
        email-address="paolo@test.com"
        zuhause="E Straße"
      ></friend-contact>
      <friend-contact
        name="Martin Beer"
        phone-number="0664 0121 120461"
        email-address="Martin.Beer@gmail.com"
        zuhause="Schoppanou"
      ></friend-contact>
    </ul>

    <header>
      <h1>Liste mit v-for</h1>
    </header>
    <ul>
      <friend-contact
        v-for="friend in friends"
        :key="friend.id"
        :name="friend.name"
        :phone-number="friend.phone"
        :email-address="friend.email"
        :is-favorite="friend.isFavorite"
      ></friend-contact>
    </ul>
  </section>
</template>

<script>
import FriendContact from "./components/FriendContact.vue";
import NewFriend from "./components/NewFriend.vue";

export default {
  components: {
    FriendContact,
    NewFriend,
  },
  data() {
    return {
      friends: [
        {
          id: "manuel",
          name: "Manuell Lorenz",
          phone: "0123 45678 90",
          email: "manuel@localhost.com",
          isFavorite: "1",
        },
        {
          id: "julie",
          name: "Julie Jones",
          phone: "0987 654421 21",
          email: "julie@localhost.com",
          isFavorite: "0",
        },
        {
          id: "antonio",
          name: "Antonio Conte",
          phone: "3212 213 456",
          email: "antonio@localhost.com",
          isFavorite: "0",
        },
        {
          id: "antonio2",
          name: "Antonio Conte",
          phone: "3212 213 456",
          email: "antonio@localhost.com",
          isFavorite: "0",
        },
      ],
    };
  },
};
</script>

<style>
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
  background-color: #58004d;
  color: white;
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
  color: #58004d;
  margin: 0 0 1rem 0;
}
button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  margin-left: 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
button:hover,
button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>
