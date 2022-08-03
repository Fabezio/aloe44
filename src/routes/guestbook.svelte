<script>
  import Head from "$lib/components/Head.svelte";
  import Fields from "$lib/components/Form/Fields.svelte";
  import Form from "$lib/components/Form/Form.svelte";
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
  function handleKey (e) {
    // console.log("e1",e1.key)
    // console.log("e2",e2.key)
    if ((e.key=="Ctrl" || e.key=="Meta") && e.key == "Enter") {
      submitForm()
    }
  }
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
    civil = ""
    firstname = ""
    lastname = ""
    phone = ""
    email = ""
    message = ""
    return data
  }
</script>

<Head title="Livre d'or" />
<svelte:window on:keydown={handleKey} />

<section class="mx-center">
  <p>
    <!-- Livre d'Or Aloe44.com
    <br> -->
    Merci de nous faire parvenir vos témoignages / anecdotes !
    <br>
    Connectez-vous à Google pour enregistrer votre progression. <a href="#" >En savoir plus</a>
    <br>
  </p>
</section>
<section>
  <Form on:submit={submitForm} >
      <Fields legend="Identité">
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
      </Fields>
      
      <!-- <Fields legend="Coordonnées géographiques" >
        <InputField bind:value={way} label="Rue"  name="way" />
        <InputField bind:value={zip} label="Code Postal" name="zip" />
        <InputField bind:value={cityname} label="Ville"  name="cityname" />
      </Fields> -->

      <Fields legend="Message" >
        <TextareaField label="Message" name="message" bind:value={message} />
      </Fields>
      
    </Form>
{#if data.length}
<pre>
  {JSON.stringify(data, null, 2)}
</pre>
{/if}
</section>

<style>
  @media (min-width: 758px) {
    .mx-center {
      width: 758px;

    }
  }
   
</style>
