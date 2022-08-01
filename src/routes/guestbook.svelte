<script>
  import Head from "$lib/components/Head.svelte";
  import InputField from "$lib/components/Form/InputField.svelte";
  import TextareaField from "$lib/components/Form/TextareaField.svelte";
  import Button from "$lib/components/Button.svelte";
  import EmojiPicker from "svelte-emoji-picker"
  let civil = ""
  let firstname = ""
  let lastname = ""
  let phone = ""
  let email = ""
  let message = ""
  let data = []
  function submitForm () {
    const newUser = {
      civil: civil,
      firstname: firstname,
      lastname: lastname,
      phone: phone,
      email: email,
      message: message
    }
    data = [...data, newUser]
    console.log(data)
    return data
  }
</script>

<Head title="Livre d'or" />

<div>
  <p>
    <!-- Livre d'Or Aloe44.com
    <br> -->
    Merci de nous faire parvenir vos témoignages / anecdotes !
    <br>
    Connectez-vous à Google pour enregistrer votre progression. <a href="#" >En savoir plus</a>
    <br>
  </p>
</div>
<section>
  <form action="" on:submit|preventDefault={submitForm}>
    <fieldset>
      <legend>Identité</legend>
      <div class="inputfield">
        <label for="civil">Etat civil</label>
        <select id="civil" bind:value={civil}>
          <option value="">--choisissez--</option>
          <option value="Monsieur">Monsieur</option>
          <option value="Madame">Madame</option>
          <option value="Mademoiselle">Mademoiselle</option>

        </select>
      </div>
      <InputField bind:value={firstname} label="Prénom" name="firstname" />
      <InputField bind:value={lastname} label="Nom" name="lastname" />
      <InputField bind:value={phone} label="Téléphone" name="phone" entryType="tel" />
      <InputField bind:value={email} label="Adresse courriel" name="email" entryType="email" />
      
  </fieldset>
  
  <fieldset>
    <legend>Commentaire</legend>
    <TextareaField label="Message" name="message" bind:value={message} />
    <!-- <EmojiPicker bind:value={message} /> -->
    
  </fieldset>
  
  <div class="flex">
    <Button submit >valider</Button>
    <Button reset >vider</Button>
    
  </div>
  
</form>
{#if data.length}
<pre>
  {JSON.stringify(data, null, 2)}
</pre>
{/if}
</section>
