<script>
  let refBoxChat;
  let refButton;
  let isActive = true;
  let isOpen = true

  function handleClick() {
    refBoxChat.style.display = 'block'
  }


</script>

<style>
  .chat-box {
    position: absolute;
    bottom: 70px;
    right: 20px;
    margin-bottom: 20px;
  }
  .chat-toggler__box {
    border: solid 1px #3287fa;
    background: #3287fa;
    width: 73px;
    height: 73px;
    border-radius: 35px 35px 0 35px;
    color: white;
    cursor: pointer;
    position: absolute;
    right: 0;
    outline: none;
  }

  .chat-group {
    display: flex;
    flex-direction: column;
    height: 76vh;
    width: 92vw;
    max-height: 49rem;
    max-width: 30rem;
    border-radius: 1.4rem;
    box-shadow: 0 0.4rem 1.4rem 0 rgba(0, 0, 0, .15);
    background-color: #fff;
    margin-bottom: 1.5rem;
    margin-right: 1.5rem;
  }

  .chat-header__box {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 5.4rem;
    background: #0082ff;
    border-top-left-radius: 1.4rem;
    border-top-right-radius: 1.4rem;
    color: white;
  }
  .notification-circle{
    position: absolute;
    top: 0;
    right: 0;
    width: 1rem;
    height: 1rem;
    border-radius: 50%;
    background-color: #3bf2bc;
  }

</style>

<div class="chat-box">
  <div class="chat-group chat-box__box" bind:this={refBoxChat}>
    <div class="chat-header__box">
      <h1 class="welcome">Welcome</h1>
    </div>
    <div class="chat-body__box">
    </div>
  </div>


  <button class="chat-toggler__box"
          on:click={handleClick}
          bind:this={refButton}>
    <svg xmlns="http://www.w3.org/2000/svg" width="23" height="23" viewBox="0 0 23 23">
      <g fill="none" fill-rule="evenodd" stroke="#FFF" stroke-linecap="round" stroke-width="2">
        <path d="M1.025 21.906l20.88-20.88M1.025 1.025l20.88 20.88"/>
      </g>
    </svg>
    {#if isActive && !isOpen}
      <span class="notification-circle"></span>
    {/if}
  </button>
</div>