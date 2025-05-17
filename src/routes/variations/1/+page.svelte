<script>
    import LayoutWrapper from '$lib/components/LayoutWrapper.svelte';
    const bgImage = '/assets/media/photos/photo27@2x.jpg'; // CORRECT
  </script>
  
  <LayoutWrapper>
    <div class="content content-full">
      <!-- Hero -->
      <div class="bg-image" style="background-image: url('{bgImage}');">
        <div class="block-content bg-white-90">
          <div class="py-3 text-center">
            <h1 class="h2 fw-bold text-black-75 mb-2">Dashboard</h1>
            <h2 class="h5 fw-medium text-muted">Hey Admin, create something amazing!</h2>
          </div>
        </div>
      </div>
      <!-- END Hero -->

      <!-- Dummy content -->
      <div class="row">
        <div class="col-sm-4">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
        <div class="col-sm-4">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
        <div class="col-sm-4">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
        <div class="col-12">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
        <div class="col-sm-6">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
        <div class="col-sm-6">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
        <div class="col-12">
          <div class="block block-rounded">
            <div class="block-content">
              <p class="text-center py-7">...</p>
            </div>
          </div>
        </div>
      </div>
      <!-- END Dummy content -->
    </div>
  </LayoutWrapper>
  