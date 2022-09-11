<script>
// @ts-nocheck
    let token = '';

    import { onMount } from 'svelte';
    import { tokenStore } from '../../stores.js';

    onMount(async () => {
        tokenStore.useLocalStorage();
        tokenStore.subscribe((value) => {
            token = value;
        });
    });

    let fileVar;
    function submitForm(){
      const dataArray = new FormData();
      dataArray.append("uploadFile", fileVar);
      fetch("https://cubich.ru/auth/UploadSkin/", {
        method: "POST",
        headers: {
					'Content-Type': 'multipart/form-data',
					'Authorization': `Bearer ${token}`
				},
        body: dataArray
      })
        .then(response => {
          console.log(response);
        })
        .catch(error => {
            console.log(error);
        });
    }
  </script>

{#if token !== ''}
    <div>
        <form on:submit={submitForm} action="#">
            <label class="custom-file-upload">
                <input type="file" bind:files={fileVar} class='load-skin'/>
                Загрузить скин
            </label>
            <br />
            <input class="submit-button" type="submit" />
        </form>
    </div>
{:else}
    <div class="need-auth">
        <h1>Загрузка скина</h1>
        <p>Для загрузки скина необходимо авторизоваться</p>
        <a href="/" class="home">На главную</a>
    </div>
{/if}

<style>
    .need-auth {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
    
    .home {
        display: block;
        margin-top: 20px;
        padding: 10px 20px;
        background-color: #007073;
        color: white;
        border-radius: 5px;
        text-decoration: none;
    }

    .need-auth h1 {
        color: white;
    }

    .need-auth p {
        color: white;
    }

    form {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
    }

    input[type="file"] {
        display: none;
    }

    

    .custom-file-upload {
        border: 1px dashed #ccc;
        display: inline-block;
        padding: 30px 90px;
        cursor: pointer;
        color: white;
        margin: 0;
    }

    .load-skin {
        display: flex;
        flex-direction: column;
    }

    .submit-button {
        margin: 0;
        background-color: #4CAF50;
        border: none;
        color: white;
        padding: 15px 32px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
    }
</style>