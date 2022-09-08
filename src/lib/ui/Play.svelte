<script>
import { goto } from "$app/navigation";


    let title = "Играть";

    function handleClick() {
		goto("/register");
	}
</script>

<button on:click={handleClick}>{title}</button>

<style>
    button {
        background-color: #007073;
        color: white;
        font-weight: 500;
        font-size: 1.5rem;
        border: 0px solid;
        padding: 10px 20px 10px 20px;
        border-radius: 15px;
    }
</style>