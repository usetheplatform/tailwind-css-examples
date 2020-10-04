<script>
  import { onDestroy } from "svelte";
  let open = false;

  function toggle() {
    open = !open;
  }

  function handleEscape(event) {
    if (event.keyCode === 27) {
      open = false;
    }
  }

  document.addEventListener("keydown", handleEscape);

  onDestroy(() => {
    document.removeEventListener("keydown", handleEscape);
  });
</script>

<div class="relative hidden ml-2 sm:block">
  <button
    on:click={toggle}
    class="relative z-10 block w-8 h-8 overflow-hidden border-2 border-gray-700 rounded-full focus:outline-none focus:border-white">
    <img
      class="object-cover object-center w-full h-full"
      src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=256&q=80"
      alt="Your account" />
  </button>

  {#if open}
    <button
      tabindex={-1}
      on:click={toggle}
      aria-label="Close menu"
      class="fixed inset-0 w-full h-full bg-black border-none shadow-none opacity-50 cursor-default" />
    <div class="absolute right-0 w-48 py-2 mt-2 bg-white rounded-lg shadow-lg">
      <a
        href="#"
        class="block px-4 py-2 text-gray-800 hover:bg-indigo-500 hover:text-white">Account
        Settings</a>
      <a
        href="#"
        class="block px-4 py-2 text-gray-800 hover:bg-indigo-500 hover:text-white">Support</a>
      <a
        href="#"
        class="block px-4 py-2 text-gray-800 hover:bg-indigo-500 hover:text-white">Sign
        out</a>
    </div>
  {/if}
</div>
