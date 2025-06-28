<script>
    import AppHeader from "@/components/AppHeader.vue";
    import '@fortawesome/fontawesome-free/css/all.min.css';
      export default {
          components: {
            AppHeader,
          }, 
      }
</script>
      <template>
        <div id="app">
          <AppHeader />

          <div class="container mt-3">
            <router-view />
          </div>
        </div>
      </template>

      <style>
        .page {
          max-width: 400px;
          margin: auto;
        }
        </style>
