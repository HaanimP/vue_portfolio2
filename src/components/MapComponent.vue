<template>
    <div class="map-container">
      <!-- The map will be displayed here -->
      <div id="map"></div>
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
      // Load the Google Maps API script
      const script = document.createElement('script');
      script.src = `https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY&callback=initMap`;
      script.async = true;
      script.defer = true;
      document.head.appendChild(script);
      script.onload = this.initMap;
    },
    methods: {
      initMap() {
        // Coordinates for Pelican Park, Cape Town
        const pelicanPark = { lat: -34.049161, lng: 18.510033 };
  
        // Create a new map centered on Pelican Park
        const map = new google.maps.Map(document.getElementById('map'), {
          center: pelicanPark,
          zoom: 15, // You can adjust the zoom level
        });
  
        // Add a marker for Pelican Park
        const marker = new google.maps.Marker({
          position: pelicanPark,
          map: map,
          title: 'Pelican Park, Cape Town',
        });
      },
    },
  };
  </script>
  
  <style scoped>
  .map-container {
    margin-top: 20px;
    width: 100%;
    height: 300px; /* Set the height as needed */
  }
  </style>
  