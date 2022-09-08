<script>
  let data = {};


  async function handleSubmit() {
    // @ts-ignore
    const data = new FormData(document.querySelector('form'));
    const user = data.get('userName');
    const pwd = data.get('password');
    const pwdConfirm = data.get('passwordConfirm');
    console.log(pwd);

    const jso = JSON.stringify({
      userName: user,
      password: pwd,
      passwordConfirm: pwdConfirm
    })

    console.log(jso);
    let response = await fetch('https://cubich.ru/auth/register', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: jso
        })
    
    console.log(response);
  }
</script>

<form
  name="register"
  autocomplete="on"
>
  <div class="register">
    <h1>Создать аккаунт</h1>

    <input
      type="text"
      placeholder="Никнейм"
      name="userName"
      id="userName"
      required
    />

    <input
      type="password"
      placeholder="Пароль"
      name="password"
      id="password"
      required
    />

    <input
      type="password"
      placeholder="Повторите пароль"
      name="passwordConfirm"
      id="passwordConfirm"
      required
    />

    <button type="button" class="registerbtn" on:click={handleSubmit}>Регистрация</button>
  </div>

  <div class="container signin">
    <p>Уже есть аккаунт? <a href="login" class="signin-link">Войти</a></p>
  </div>
</form>

<style>
  form {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .register {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin: 0 auto;
    padding: 10px;
    align-self: center;
    align-items: center;
  }

  h1,
  p {
    color: white;
    font-family: "Montserrat";
  }

  .signin-link {
    color: white;
    font-weight: bold;
  }

  input {
    width: 50%;
    padding: 18px 2px;
    margin: 20px 0;
    display: inline-block;
    border: 0px;
    border-bottom: 1px solid #ccc;
    box-sizing: border-box;
    background-color: transparent;
    color: white;
  }

  input:focus {
    outline: none;
  }

  .registerbtn {
    background-color: #4caf50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    cursor: pointer;
    width: 50%;
  }
</style>


<!-- <script>
import { goto } from "$app/navigation";


  let data = {};
  function handleClick() {
		alert("Click");
	}

  function download() {
    window.open("http://launcher.cubich.ru", "_blank");
  }
</script>

<form
  name="register"
  autocomplete="on"
>
  <div class="register">
    <h1>Создать аккаунт</h1>

    <input
      type="text"
      placeholder="Никнейм"
      name="username"
      id="username"
      required
    />

    <input
      type="password"
      placeholder="Пароль"
      name="password"
      id="password"
      required
    />

    <input
      type="password"
      placeholder="Повторите пароль"
      name="passwordConfirm"
      id="passwordConfirm"
      required
    />

    <button type="submit" class="registerbtn" on:click={handleClick}>Регистрация</button>
    <button class="registerbtn" on:click={download}>Скачать лаунчер</button>
  </div>

  <!-- <div class="container signin">
    <p>Уже есть аккаунт? <a href="login" class="signin-link">Войти</a></p>
  </div> -->
<!-- </form>

<style>
  form {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .register {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin: 0 auto;
    padding: 10px;
    align-self: center;
    align-items: center;
  }

  h1,
  p {
    color: white;
    font-family: "Montserrat";
  }

  .signin-link {
    color: white;
    font-weight: bold;
  }

  input {
    width: 50%;
    padding: 18px 2px;
    margin: 20px 0;
    display: inline-block;
    border: 0px;
    border-bottom: 1px solid #ccc;
    box-sizing: border-box;
    background-color: transparent;
    color: white;
  }

  input:focus {
    outline: none;
  }

  .registerbtn {
    background-color: #4caf50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    cursor: pointer;
    width: 50%;
  }
</style> --> -->
