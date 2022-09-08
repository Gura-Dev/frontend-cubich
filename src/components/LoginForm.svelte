<script>
    function closeLoginMenu() {
        document.getElementById("loginMenu").style.display = "none";
    }
</script>

<div class="loginMenu">
    <button id="closeButton" on:click={closeLoginMenu}>
        <i class="mi mi-close">
            <span class="u-sr-only" />
        </i>
    </button>
    <form>
        <div class="field">
            <label class="inputLabel" for="Nickname">Ник</label>
            <input
                type="username"
                name="username"
                class="input"
                placeholder=""
            />
        </div>

        <div class="field">
            <label class="inputLabel" for="password">Пароль</label>
            <input
                type="password"
                name="password"
                class="input"
                placeholder=""
            />
        </div>
    </form>
</div>

<style>
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

    form {
        --text-color: #afafaf;
        /* max-width: 500px; */
    }

    .loginMenu {
        padding: 20px;
        border: 1px solid #d16dff;
        border-radius: 15px;
        max-height: 600px;
    }

    #closeButton {
        font-size: 25px;
        padding: 3px;
        float: right;
        line-height: 0;
    }

    .field {
        position: relative;
        width: 100%;
        border-bottom: 2px dashed var(--text-color);
        margin: 4rem auto 1rem;
    }

    .field::after {
        content: "";
        position: relative;
        display: block;
        height: 4px;
        width: 100%;
        background: #d16dff;
        transform: scaleX(0);
        transform-origin: 0%;
        transition: transform 500ms ease;
        top: 2px;
    }

    .field:focus-within {
        border-color: transparent;
    }

    .field:focus-within::after {
        transform: scaleX(1);
    }

    .input {
        outline: none;
        border: none;
        overflow: hidden;
        margin: 0;
        width: 100%;
        padding: 0.25rem 0;
        background: none;
        color: white;
        font-size: 1.2rem;
        font-weight: bold;
    }

    .input:valid {
        color: yellowgreen;
    }

    .input:invalid {
        color: orangered;
    }
</style>
