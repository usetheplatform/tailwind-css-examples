<script>
  import Dropdown from "./Dropdown.svelte";

  let open = false;

  function toggle() {
    open = !open;
  }
</script>

<header
  class="bg-gray-900 sm:flex sm:justify-between sm:px-4 sm:py-3 sm:items-center">
  <div class="flex items-center justify-between px-4 py-3 sm:p-0">
    <div><img class="h-8" src="logo.svg" alt="Workcation" /></div>
    <div class="sm:hidden">
      <button
        on:click={toggle}
        type="button"
        class="block text-gray-500 border-none focus:text-white focus:outline-none hover:text-white">
        <svg class="w-6 h-6 fill-current" viewBox="0 0 24 24">
          {#if open}
            <path
              v-if="isOpen"
              fill-rule="evenodd"
              d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z" />
          {:else}
            <path
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z" />
          {/if}
        </svg>
      </button>
    </div>
  </div>
  <div class:hidden={!open} class="sm:block">
    <div class="px-2 pt-2 pb-4 sm:flex sm:p-0">
      <a
        class="block px-2 py-1 font-semibold text-white rounded sm:ml-2 sm:mt-0 hover:bg-gray-800"
        href="#">
        List your property</a>
      <a
        class="block px-2 py-1 mt-1 font-semibold text-white rounded sm:ml-2 sm:mt-0 hover:bg-gray-800"
        href="#">Trips</a>
      <a
        class="block px-2 py-1 mt-1 font-semibold text-white rounded sm:ml-2 sm:mt-0 hover:bg-gray-800"
        href="#">Messages</a>
      <Dropdown />
    </div>
    <div class="px-4 py-5 border-t border-gray-800 sm:hidden">
      <div class="flex items-center">
        <img
          class="object-cover object-center w-8 h-8 border border-gray-600 rounded-full"
          src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=256&q=80"
          alt="Your account" />
        <span class="ml-3 font-semibold text-white">Jane Doe</span>
      </div>
      <div class="mt-4">
        <a href="#" class="block mt-2 text-gray-400 hover:text-white">Account
          Settings</a>
        <a
          href="#"
          class="block mt-2 text-gray-400 hover:text-white">Support</a>
        <a href="#" class="block mt-2 text-gray-400 hover:text-white">Sign out</a>
      </div>
    </div>
  </div>
</header>
