<!--	Bonus: If a password is clicked, remove it from the list. -->
<script>
    let password = '';
    let passwords = [];
    $: passwordLength = password.length; 
	
    function addPassword(){
        passwords = [...passwords, password];
        console.log(passwords);
        console.log(password);
        console.log(passwordLength);
    }
    function removePassword(index){
        passwords = passwords.filter((password, idx) => {return idx !== index;});
        console.log(idx);
    }
</script>

<main>
    <div>
        <h1>Write your password</h1>
        <input type="password" bind:value={password} />

        {#if passwordLength < 5}
            <p>Password to short, minimium of 5</p>
        {:else if passwordLength > 10}
            <p>Password to long, maxmium of 10</p>
        {:else} 
        
        <button on:click={addPassword}>
            Add a Password
        </button>

        <p>{password}</p>
        {/if}
        
        <ul>
        {#each passwords as password, i (password)}
        <li on:click={removePassword.bind(this, i)}>{password}</li>
        {/each}
        </ul>
    
    </div>
</main>

<style>
</style>
