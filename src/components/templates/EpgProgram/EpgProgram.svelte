<script>
  export let channelList;
  export let currentCol;
  export let currentRow;
  export let progWidth;
  export let xPos;
  export let yPos;
</script>

<style>
  .channelName {
    display: flex;
    flex-wrap: wrap;
  }

  .activeChannel .activeProgram {
    background-color: rgba(255, 255, 255, 0.5);
    font-weight: bold;
    font-size: 17px;
    overflow: hidden;
  }
  .channelName {
    display: flex;
    flex-wrap: wrap;
    padding: 0;
    margin: 0px;
  }
  .channelName li {
    list-style: none;
    font-family: "Arial", "Verdana";
    color: #fff;
    padding: 20px 10px;
    box-sizing: border-box;
    border: solid 1px #fff;
    height: 78px;
    transition:font-weight,font-size 300ms linear;
    display: flex;
    align-items: center;
  }
  .epgWrapper {
    width: 4900px;
    position: absolute;
    left: 0;
    top: 0;
    transition: transform 300ms linear;
  }
</style>

<div class="epgWrapper" style={`transform:translate3d(${xPos}px,${yPos}px,0)`}>
  {#each channelList as channel, index}
    <ul
      class={index === currentRow ? 'channelName activeChannel' : 'channelName'}>
      {#each channel.events as program, i}
        <li class={i === currentCol ? 'programName activeProgram' : 'programName'} style={`width:${progWidth}px`}>
          {program.eventName} </li>
      {/each}
    </ul>
  {/each}
</div>
