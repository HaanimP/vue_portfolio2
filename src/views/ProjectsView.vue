<template>
  <div class="container mt-5 mb-5">
    <section class="row row-cols-1 row-cols-md-3 g-4">
      <div v-for="project in $store.state.projects" :key="project.id" class="col animate__animated animate__backInLeft">
        <div class="card h-100">
          <img :src="project.image" class="card-img-top" alt="Project Image" />
          <div class="card-body d-flex flex-column justify-content-between" style="font-family: 'Merriweather', serif;">
            <div>
              <h5 class="card-title font-weight-bold">{{ project.title }}</h5>
              <p class="card-text">{{ project.description }}</p>
            </div>
            <div class="d-flex justify-content-center align-items-center">
              <div class="project-links d-flex justify-content-center">
                <h6 v-if="project.Github" class="me-3"><a :href="project.Github" target="_blank">GitHub</a></h6>
                <h6 v-if="project.Vercel"><a :href="project.Vercel" target="_blank">Vercel</a></h6>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import 'animate.css';
import { mapActions } from "vuex";

export default {
  computed: {
    fetchProjects() {
      this.$store.dispatch('fetchProjects')
    }
  },
  methods: {
    ...mapActions("projects", ["fetchProjects"]),
  },
  mounted() {
    this.fetchProjects
  },
};
</script>

<style scoped>
body {
  background-image: url("https://i.ibb.co/ZNZ01VK/port-pro.jpg");
  background-size: cover;
  background-position: center;
  font-family: 'Merriweather', serif;
}

.card {
  border: none;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s;
}

.card:hover {
  transform: scale(1.05);
}

.card-body {
  padding: 1.25rem;
}

.card-title {
  color: #000;
}

.card-text {
  color: #6c757d;
}

.btn-link {
  color: #6c757d;
  text-decoration: none;
}

.btn-link:hover {
  text-decoration: underline;
}

.project-links h6 {
  margin: 0;
}

.project-links a {
  color: #000;
  text-decoration: none;
  font-weight: bold;
}
</style>