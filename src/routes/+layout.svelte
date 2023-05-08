<script>
  import Drawer from "./drawer.svelte";
  import "../app.css";

</script>

<div class="navbar bg-base-100">
  <div class="flex-none">
    <button class="btn btn-square btn-ghost">
      <label for="my-drawer" class="drawer-button">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          class="inline-block w-5 h-5 stroke-current"
          ><path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          /></svg
        >
      </label>
    </button>
  </div>
  <div class="flex-1">
    <a class="btn btn-ghost normal-case text-xl">Reactive Programming</a>
  </div>
</div>
<slot />
<div class="drawer">
  <input id="my-drawer" type="checkbox" class="drawer-toggle" />
  <div class="drawer-content">
    <!-- Page content here -->
  </div>
  <div class="drawer-side">
    <label for="my-drawer" class="drawer-overlay" />
    <ul class="menu p-4 w-80 bg-base-100 text-base-content">
      <!-- Sidebar content here -->
      <li><a href="/introduction">Reactive Programming</a></li>
      <li><a>Rx.net</a></li>
      <li><a>Rxjs</a></li>
      <li><a>Reference Links</a></li>
    </ul>
  </div>
</div>


<style lang="postcss">
  :global(html) {
    background-color: theme(colors.gray.100);
  }
</style>
