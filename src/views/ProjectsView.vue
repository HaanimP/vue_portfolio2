<template>
    <div class="main2">
        <div v-for="project in $store.state.projects" v-bind:key="project.id" class="project-card animate__animated animate__backInLeft">
        <div class="card-header">
            <h2 class="project-details">{{ project.title }}</h2><br>
        </div>
        <div class="card-body">
            <img :src=" project.image" class="project-image"><br><br>
            <p class="project-details">{{ project.description }}</p>
        </div>
        <div class="card-footer">
            <div class="project-links">
            <h4 v-if="project.Github"><a :href="project.Github" target="_blank">GitHub</a></h4>
            <h4 v-if="project.Vercel"><a :href="project.Vercel" target="_blank">Vercel</a></h4>
          </div>
        </div>
        </div>
    </div>
    </template>
    <script>
    import 'animate.css';
    import { mapGetters, mapActions } from "vuex";
    export default {
        // data(){
        //     return{
        //         projectData: jsonData
        //     }
        // },
        computed: {
        // ...mapGetters("projects", ["getProjects"]),
        fetchProjects(){
            this.$store.dispatch('fetchProjects')
        }
      },
      methods: {
        // ...mapActions("projects", ["fetchProjects"]),
      },
      mounted() {
        this.fetchProjects
      },
    };
    </script>
    <style scoped>
    .main2 {
      display: flex;
      justify-content: space-around;
      flex-wrap: wrap;
    }
    
    .project-card {
      border: 1px solid #ddd;
      border-radius: 8px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      margin: 16px;
      width: 300px;
      transition: transform 0.3s;
    }
    
    .project-card:hover {
      transform: scale(1.05);
    }
    
    .card-container {
      display: flex;
      flex-direction: column;
      height: 100%;
    }
    
    .card-header,
    .card-body,
    .card-footer {
      padding: 16px;
    }
    
    .card-header {
      color: #fff;
      background: #987554;
      text-align: center;
      border-top-left-radius: 8px;
      border-top-right-radius: 8px;
    }
    
    .project-image {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 8px;
    }
    
    p.project-details {
      color: #D2B48C;
    }
    
    .project-details {
      margin-top: 0;
    }
    
    .card-footer {
      flex: 1; /* Expand to fill available space */
      display: flex;
      flex-direction: column;
      background-color: #987554;
      border-bottom-left-radius: 8px;
      border-bottom-right-radius: 8px;
    }
    
    .project-links {
  margin-top: auto; /* Push content to the bottom of the .card-footer */
  text-align: center;
}
    
    .project-links h4 {
  margin: 0;
}
    
    .project-links a {
      color: #D2B48C;
      text-decoration: none;
      font-weight: bold;
    }

    .project-links a:not(:last-child) {
  margin-right: 10px; /* Adjust the spacing between links */
}
    
    @media (min-width: 768px) {
  .project-card {
    width: calc(25% - 15px); 
  }
}

    
    @media (max-width: 480px) {
      .project-card {
        width: 100%;
      }
    }
    
    .project-card:hover {
      transform: scale(1.05);
    }
    
    .card-container {
      display: flex;
      flex-direction: column;
      height: 100%;
    }
    
    .card-header,
    .card-body,
    .card-footer {
      padding: 16px;
    }
    
    .card-header {
      color: #fff;
      background: #987554;
      text-align: center;
      border-top-left-radius: 8px;
      border-top-right-radius: 8px;
    }
    
    .project-image {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 8px;
    }
    
    p.project-details {
      color: #D2B48C;
    }
    
    .project-details {
      margin-top: 0;
    }
    
    .card-footer {
      flex: 1; /* Expand to fill available space */
      display: flex;
      flex-direction: column;
      background-color: #987554;
      border-bottom-left-radius: 8px;
      border-bottom-right-radius: 8px;
    }
    
    .project-links {
      margin-top: auto; /* Push content to the bottom of the .card-footer */
    }
    
    .project-links h4 {
      margin: 0;
    }
    
    .project-links a {
      color: #D2B48C;
      text-decoration: none;
      font-weight: bold;
    }
    </style>