<script>
  export let data;
  export let currentMenu;
</script>

<style>
  li {
    list-style: none;
    font-size: 30px;
    color: #fff;
    font-family: Arial, Helvetica, sans-serif;
    padding: 20px;
    text-align: center;
    border: solid 1px rgba(255, 255, 255, 0);
  }
  .active {
    border: solid 1px rgba(255, 255, 255, 1);
    background: rgba(255, 255, 255, 0.1);
  }
</style>

{#each data as menu, index}
  <li class={index === currentMenu ? 'active' : ''}> {menu} </li>
{/each}
