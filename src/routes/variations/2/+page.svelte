<script>
  import LayoutWrapper from '$lib/components/LayoutWrapper.svelte';
  // Option 1: Use absolute path (uncomment if not using import)
  // const bgImage = '/assets/media/photos/photo27@2x.jpg';

  // Option 2: Import the image for build-time optimization
  const bgImage = '/assets/media/photos/photo27@2x.jpg'; // CORRECT
    
  </script>
  
  <LayoutWrapper>
    <div class="bg-image" style="background-image: url('{bgImage}');">
      <div class="bg-white-90">
        <div class="content text-center">
          <div class="pt-5 pb-3">
            <h1 class="h2 fw-bold text-black-75 mb-2">Dashboard</h1>
            <h2 class="h5 fw-medium text-muted">Everything looks nice and smooth!</h2>
          </div>
        </div>
      </div>
    </div>
    <!-- END Hero -->

    <!-- Page Content -->
    <div class="content content-full">
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
  