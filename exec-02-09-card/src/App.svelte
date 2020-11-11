<script>
    import ContactCard from './ContactCard.svelte';
    
    let name;
    let jobTitle;
    let shortDescription;
    let imageURL;

    $: console.log(name);
    $: console.log(jobTitle);
    $: console.log(shortDescription);
    $: console.log(imageURL)

</script>

<main>
    <div>
        <h1>Contact App</h1>
        <h2>Contact information on a glance</h2>
    </div>
    
    <div>
        <p>Write your name:</p>
        <input type="text" bind:value={name} />
    </div>
    <div>
        <p>Write your job title:</p>
        <input type="text" bind:value={jobTitle} />
    </div>
    
    <div>
        <p>Write your a short description:</p>
        <input type="text" bind:value={shortDescription} />
    </div>

    <div>
        <p>Paste your image URL:</p>
        <input type="url" bind:value={imageURL} />
    </div>

    <ContactCard userName={name} userTitle={jobTitle} userDescription={shortDescription} userImage={imageURL}/>


</main>

<style>
</style>
