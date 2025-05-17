<script>
    import LayoutWrapper from '$lib/components/LayoutWrapper.svelte';
    const videoMp4 = '/assets/media/videos/city_night.mp4';
    const videoWebm = '/assets/media/videos/city_night.webm';
    const videoOgv = '/assets/media/videos/city_night.ogv';
    const posterSrc = '/assets/media/videos/city_night.jpg';

    // Log for debugging
    console.log('Video MP4:', videoMp4);
    console.log('Video WebM:', videoWebm);
    console.log('Video OGV:', videoOgv);
    console.log('Poster:', posterSrc);
  </script>
  
  <LayoutWrapper>
    <div class="bg-video" data-vide-bg="assets/media/videos/city_night" data-vide-options="posterType: jpg" style="position: relative;">
      <div style="position: absolute; z-index: -1; inset: 0px; overflow: hidden; background-size: cover; background-color: transparent; background-repeat: no-repeat; background-position: 50% 50%; background-image: none;">
       <video
            autoplay
            loop
            muted
            style="margin: auto; position: absolute; z-index: -1; top: 50%; left: 50%; transform: translate(-50%, -50%); visibility: visible; opacity: 1; width: 1907px; height: auto;"
            playsinline
            poster={posterSrc}
          >
            <source src={videoMp4} type="video/mp4" />
            <source src={videoWebm} type="video/webm" />
            <source src={videoOgv} type="video/ogg" />
          </video>
        </div>
      <div class="bg-primary-dark-op">
        <div class="content text-center">
          <div class="pt-5 pb-3">
            <h1 class="h2 fw-bold text-white mb-2">Dashboard</h1>
            <h2 class="h5 fw-medium text-white-75">Welcome to your own SaaS!</h2>
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
  