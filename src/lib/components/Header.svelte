<script>
  import { page } from '$app/stores';
  import { onMount } from 'svelte';
  
  $: currentPath = $page.url.pathname;
  const isParentActive = (prefix) => currentPath.startsWith(prefix) ? 'active' : '';
  
  // State to control search overlay visibility
  let searchVisible = false;
  let searchInput;
  
  // State to control theme dropdown visibility
  let themeDropdownVisible = false;
  
  // Function to toggle search section
  function toggleSearch(action) {
    if (action === 'on') {
      searchVisible = true;
      // Focus the input after the DOM updates
      setTimeout(() => {
        if (searchInput) searchInput.focus();
      }, 100);
    } else if (action === 'off') {
      searchVisible = false;
    }
  }
  
  // Function to toggle theme dropdown
  function toggleThemeDropdown() {
    themeDropdownVisible = !themeDropdownVisible;
  }
  
  // Function to apply a theme
  function applyTheme(theme) {
    // You can implement theme switching logic here
    console.log('Applying theme:', theme);
    
    // Close dropdown after selection (optional)
    // themeDropdownVisible = false;
  }
  
  // Handle keyboard events for ESC key
  function handleKeydown(event) {
    if (event.key === 'Escape' && searchVisible) {
      toggleSearch('off');
    }
  }
  
  // Function to handle click outside dropdown
  function handleClickOutside(event) {
    // Check if click is outside the theme dropdown
    const themeDropdown = document.getElementById('page-header-themes-dropdown');
    const themeDropdownMenu = document.querySelector('.dropdown-menu[aria-labelledby="page-header-themes-dropdown"]');
    
    if (themeDropdownVisible && 
        themeDropdown && 
        themeDropdownMenu && 
        !themeDropdown.contains(event.target) && 
        !themeDropdownMenu.contains(event.target)) {
      themeDropdownVisible = false;
    }
  }
  
  onMount(() => {
    // Add event listener for keyboard events
    window.addEventListener('keydown', handleKeydown);
    // Add event listener for clicks outside dropdown
    window.addEventListener('click', handleClickOutside);
    
    // Cleanup when component is destroyed
    return () => {
      window.removeEventListener('keydown', handleKeydown);
      window.removeEventListener('click', handleClickOutside);
    };
  });
</script>
<header id="page-header">
  <!-- Header Content -->
  <div class="content-header">
    <!-- Left Section -->
    <div class="space-x-1">
      <!-- Logo -->
      <a class="link-fx fw-bold" href="/">
        <i class="fa fa-fire text-primary"></i>
        <span class="fs-4 text-dual">code</span><span class="fs-4 text-primary">base</span>
      </a>
      <!-- END Logo -->
    </div>
    <!-- END Left Section -->

    <!-- Middle Section -->
    <div class="d-none d-lg-block">
      <!-- Header Navigation -->
      <!-- Desktop Navigation, mobile navigation can be found in #sidebar -->
      <ul class="nav-main nav-main-horizontal nav-main-hover">
        <li class="nav-main-item">
          <a class="nav-main-link {currentPath === '/' ? 'active' : ''}" href="/">
            <i class="nav-main-link-icon fa fa-house-user"></i>
            <span class="nav-main-link-name">Dashboard</span>
          </a>
        </li>
        <li class="nav-main-heading">Layout</li>
        <li class="nav-main-item">
          <a class="nav-main-link  nav-main-link-submenu {isParentActive('/variations')}" data-toggle="submenu" aria-haspopup="true" aria-expanded="true" href="#">
            <i class="nav-main-link-icon fa fa-puzzle-piece"></i>
            <span class="nav-main-link-name">Variations</span>
          </a>
          <ul class="nav-main-submenu">
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/1' ? 'active' : ''}" href="/variations/1">
                <span class="nav-main-link-name">Hero Simple 1</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/2' ? 'active' : ''}" href="/variations/2">
                <span class="nav-main-link-name">Hero Simple 2</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/3' ? 'active' : ''}" href="/variations/3">
                <span class="nav-main-link-name">Hero Simple 3</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/4' ? 'active' : ''}" href="/variations/4">
                <span class="nav-main-link-name">Hero Simple 4</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/5' ? 'active' : ''}" href="/variations/5">
                <span class="nav-main-link-name">Hero Image 1</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/6' ? 'active' : ''}" href="/variations/6">
                <span class="nav-main-link-name">Hero Image 2</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/7' ? 'active' : ''}" href="/variations/7">
                <span class="nav-main-link-name">Hero Image 3</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/8' ? 'active' : ''}" href="/variations/8">
                <span class="nav-main-link-name">Hero Image 4</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/9' ? 'active' : ''}" href="/variations/9">
                <span class="nav-main-link-name">Hero Video 1</span>
              </a>
            </li>
            <li class="nav-main-item">
              <a class="nav-main-link {currentPath === '/variations/10' ? 'active' : ''}" href="/variations/10">
                <span class="nav-main-link-name">Hero Video 2</span>
              </a>
            </li>
          </ul>
        </li>
        <li class="nav-main-heading">Other Pages</li>
        <li class="nav-main-item">
          <a class="nav-main-link {currentPath === '/search' ? 'active' : ''}" href="/search">
            <i class="nav-main-link-icon fa fa-search"></i>
            <span class="nav-main-link-name">Search</span>
          </a>
        </li>
        <li class="nav-main-item">
          <a class="nav-main-link" href="/">
            <i class="nav-main-link-icon fa fa-arrow-left"></i>
            <span class="nav-main-link-name">Go Back</span>
          </a>
        </li>
      </ul>
      <!-- END Header Navigation -->
    </div>
    <!-- END Middle Section -->

    <!-- Right Section -->
    <div class="space-x-1">
      <!-- Color Themes -->
      <!-- Themes functionality initialized in Template._uiHandleTheme() -->
      <div class="dropdown d-inline-block" role="group">
        <button 
          type="button" 
          class="btn btn-sm btn-alt-secondary"
          class:show={themeDropdownVisible}
          id="page-header-themes-dropdown" 
          on:click={toggleThemeDropdown}
          aria-haspopup="true" 
          aria-expanded={themeDropdownVisible}
        >
          <i class="fa fa-fw fa-paint-brush"></i>
        </button>
        <div 
          class="dropdown-menu dropdown-menu-end dropdown-menu-lg p-0"
          class:show={themeDropdownVisible}
          aria-labelledby="page-header-themes-dropdown" 
          style={themeDropdownVisible ? "position: absolute; inset: 0px 0px auto auto; margin: 0px; transform: translate(0px, 33px);" : ""}
          data-popper-placement="bottom-end"
        >
          <div class="p-3 bg-body-light rounded-top">
            <h5 class="h6 text-center mb-0">
              Color Themes
            </h5>
          </div>
          <div class="p-3">
            <div class="row g-0 text-center mb-1">
              <div class="col-2 mb-1">
                <a class="text-default" href="javascript:void(0)" on:click={() => applyTheme('default')}>
                  <i class="fa fa-2x fa-circle"></i>
                </a>
              </div>
              <div class="col-2 mb-1">
                <a class="text-elegance" href="javascript:void(0)" on:click={() => applyTheme('elegance')}>
                  <i class="fa fa-2x fa-circle"></i>
                </a>
              </div>
              <div class="col-2 mb-1">
                <a class="text-pulse" href="javascript:void(0)" on:click={() => applyTheme('pulse')}>
                  <i class="fa fa-2x fa-circle"></i>
                </a>
              </div>
              <div class="col-2 mb-1">
                <a class="text-flat" href="javascript:void(0)" on:click={() => applyTheme('flat')}>
                  <i class="fa fa-2x fa-circle"></i>
                </a>
              </div>
              <div class="col-2 mb-1">
                <a class="text-corporate" href="javascript:void(0)" on:click={() => applyTheme('corporate')}>
                  <i class="fa fa-2x fa-circle"></i>
                </a>
              </div>
              <div class="col-2 mb-1">
                <a class="text-earth" href="javascript:void(0)" on:click={() => applyTheme('earth')}>
                  <i class="fa fa-2x fa-circle"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- END Color Themes -->

      <!-- Open Search Section -->
      <!-- Layout API, functionality initialized in Template._uiApiLayout() -->
      <button 
      type="button" 
      class="btn btn-sm btn-alt-secondary" 
      on:click={() => toggleSearch('on')}
    >
      <i class="fa fa-fw fa-search"></i>
    </button>
      <!-- END Open Search Section -->

      <!-- Toggle Sidebar -->
      <!-- Layout API, functionality initialized in Template._uiApiLayout() -->
      <button type="button" class="btn btn-sm btn-alt-secondary d-lg-none" data-toggle="layout" data-action="sidebar_toggle">
        <i class="fa fa-fw fa-bars"></i>
      </button>
      <!-- END Toggle Sidebar -->
    </div>
    <!-- END Right Section -->
  </div>
  <!-- END Header Content -->

  <!-- Header Search -->
  <div 
  id="page-header-search" 
  class="overlay-header bg-body-extra-light"
  class:show={searchVisible}
>
  <div class="content-header">
    <form class="w-100" action="bd_search.html" method="POST">
      <div class="input-group">
        <!-- Close Search Section -->
        <button 
          type="button" 
          class="btn btn-secondary" 
          on:click={() => toggleSearch('off')}
        >
          <i class="fa fa-fw fa-times"></i>
        </button>
        <!-- END Close Search Section -->
        <input 
          type="text" 
          class="form-control" 
          placeholder="Search or hit ESC.." 
          id="page-header-search-input" 
          name="page-header-search-input"
          bind:this={searchInput}
        >
        <button type="submit" class="btn btn-secondary">
          <i class="fa fa-fw fa-search"></i>
        </button>
      </div>
    </form>
  </div>
</div>
  <!-- END Header Search -->

  <!-- Header Loader -->
  <!-- Please check out the Activity page under Elements category to see examples of showing/hiding it -->
  <div id="page-header-loader" class="overlay-header bg-primary">
    <div class="content-header">
      <div class="w-100 text-center">
        <i class="far fa-sun fa-spin text-white"></i>
      </div>
    </div>
  </div>
  <!-- END Header Loader -->
</header>