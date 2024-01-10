<template>
  <div class="home">
    <div class="row" v-if="HomeArray && HomeArray.length > 0">
      <div class="col-4">
        <div class="webDeveloperTitle">
          <h1>{{ HomeArray[0].title }}</h1>
        </div>
        <div class="greeting">
          <h1>{{ HomeArray[0].greeting.text }} <span class="nameSpan">{{ HomeArray[0].greeting.name }}</span></h1>
          <router-link to="/contact" class="contact-button">{{ HomeArray[0].contactButton }}</router-link>
        </div>
      </div>

      <div class="col-4">
        <div class="professionalImage">
          <img :src="HomeArray[0].imageSrc" alt="Professional Image">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  components: {},
  computed: {
    HomeArray() {
      // Ensure that HomeArray is always an array
      return this.$store.state.home || [];
    }
  },
  mounted() {
    // Dispatch the fetchHome action when the component is mounted
    this.$store.dispatch('fetchHome');
  }
}
</script>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-image: url('https://i.postimg.cc/SNd2jJ44/9819e40ef04dc567e18c4c7b150cb2f5.jpg');
  background-size: cover;
  background-position: center;
  color: #D2B48C;
}

.row {
  display: flex;
  width: 100%;
}

.col-4 {
  flex: 0 0 33.33%;
}

.webDeveloperTitle {
  text-align: left;
  padding-left: 20px;
}

.webDeveloperTitle h1 {
  font-weight: 800;
  font-size: 24px;
  margin-bottom: 10px;
  color: #D2B48C;
}

.professionalImage {
  text-align: center;
}

.professionalImage img {
  width: 100%;
  max-width: 300px;
  height: auto;
  border-radius: 5%;
}

.greeting {
  text-align: right;
  padding-right: 20px;
}

.greeting h1 {
  color: #A88B63;
  font-weight: 600;
  margin: 0;
}

.nameSpan {
  color: #BFAE94;
  font-weight: bold;
}

.contact-button {
  display: inline-block;
  background-color: #A88B63;
  color: #fff;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
  margin-top: 10px;
  transition: background-color 0.3s ease;
}

.contact-button:hover {
  background-color: #664229;
}

@media only screen and (max-width: 768px) {
  .row {
    flex-direction: column;
  }

  .col-4 {
    flex: 1;
    width: 100%;
  }

  .greeting {
    text-align: left;
    margin-right: 0;
    padding-left: 20px;
    padding-right: 20px;
  }

  .greeting h1 {
    color: #D2B48C;
    font-weight: bolder;
  }
}

@media only screen and (max-width: 1024px) {
  .col-4 {
    flex: 1;
    width: 100%;
  }
}
</style>