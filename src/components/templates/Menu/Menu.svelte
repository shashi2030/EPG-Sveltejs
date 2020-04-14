<script>
  import { fly } from "svelte/transition";
  import Menuitem from "../../atoms/menuitem/menuitem.svelte";
  export let data;
  export let currentMenu;
</script>

<style>
  ul {
    width: 500px;
    height: 300px;
    padding: 200px 0 0 0;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: rgba(0, 0, 0, 1);
  }
</style>

<ul transition:fly={{ x: -800, duration: 500 }}>
  <Menuitem {data} {currentMenu} />
</ul>
