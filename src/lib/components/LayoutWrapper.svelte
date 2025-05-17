<script>
    import Sidebar from './Sidebar.svelte';
    import Header from './Header.svelte';
    import Footer from './Footer.svelte';
  </script>
  
  <div id="page-container" class="sidebar-dark side-scroll page-header-fixed page-header-dark main-content-boxed">
    <Sidebar />
    <Header />
    <main id="main-container">
      <slot /> <!-- Slot ini untuk isi halaman -->
    </main>
    <Footer />
  </div>
  