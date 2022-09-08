<script>
  import LoginForm from "./LoginForm.svelte";

  let logoSrc = "/img/logo.png";
  let name = "Кубыч";

  let user = { loggedIn: false };

  function openLoginMenu() {
    document.getElementById("loginMenu").style.display = "flex";
  }

  function toggle() {
    user.loggedIn = !user.loggedIn;
  }
</script>

<svelte:head>
  <link
    rel="stylesheet"
    href="https://unpkg.com/mono-icons@1.0.5/iconfont/icons.css"
  />
</svelte:head>

<header>
  <img src={logoSrc} alt="" class="logo" />
  <div class="name">{name}</div>
  <div class="separator" />

  <div class="menu-button main">Главная</div>
  <div class="menu-button map">Карта</div>
  <div class="menu-button rules">Правила</div>

  {#if user.loggedIn}
    <button on:click={toggle}> Выйти </button>
  {/if}

  {#if !user.loggedIn}
    <button on:click={openLoginMenu}> Войти </button>
  {/if}
</header>

<div class="loginWraper" id="loginMenu">
  <LoginForm />
</div>

<style>
  header {
    display: flex;
    align-items: center;
    padding: 0 20px;
    height: 60px;
    background-color: #151319;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  button {
    margin-left: auto;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    background-color: #151319;
    color: #fff;
    font-size: 16px;
    cursor: pointer;
  }

  button:hover {
    background-color: #1f1f24;
  }

  .loginWraper {
    display: none;
    position: fixed;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
    justify-content: center;
    align-items: center;
    backdrop-filter: blur(1rem);
  }

  .logo {
    width: 45px;
    height: 45px;
    border-radius: 50%;
    cursor: pointer;
  }

  .name {
    margin-left: 20px;
    font-size: 1.5rem;
    font-weight: 400;
    color: white;
    font-family: "Montserrat", sans-serif;
    cursor: pointer;
  }

  .separator {
    border-left: 2px solid white;
    height: 50%;
    margin-left: 20px;
    margin-right: 20px;
  }

  .menu-button {
    font-size: 1rem;
    font-weight: 400;
    color: #c7c7d6;
    font-family: "Montserrat", sans-serif;
    cursor: pointer;
    margin: 10px;
  }

  .menu-button:hover {
    color: white;
  }
</style>
