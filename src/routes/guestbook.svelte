<script>
  import Fields from "$lib/components/Form/Fields.svelte";
  import Form from "$lib/components/Form/Form.svelte";
  import InputField from "$lib/components/Form/InputField.svelte";
  import TextareaField from "$lib/components/Form/TextareaField.svelte";
  import Select from "$lib/components/Form/Select.svelte";
  import Button from "$lib/components/Button.svelte";
  import EmojiPicker from "svelte-emoji-picker"
  let title = ""
  let firstname = ""
  let lastname = ""
  let phone = ""
  let email = ""
  let message = ""
  let data = []
  const loginUrl = "https://accounts.google.com/Login?continue=https%3A%2F%2Fdocs.google.com%2Fforms%2Fd%2Fe%2F1FAIpQLSe25B5v88PXWpsiGluOIJHCo6GXW5pHxl9Hp_ZLEnoxrLeW5g%2Fviewform%3Ffbzx%3D-2931820339718156179"
  function handleKey (e) {
    // console.log("e1",e1.key)
    // console.log("e2",e2.key)
    if ((e.key=="Ctrl" || e.key=="Meta") && e.key == "Enter") {
      submitForm()
    }
  }
  function submitForm () {
    const newUser = {
      title: title,
      firstname: firstname,
      lastname: lastname,
      phone: phone,
      email: email,
      message: message
    }
    data = [...data, newUser]
    console.log(data)
    title = ""
    firstname = ""
    lastname = ""
    phone = ""
    email = ""
    message = ""
    return data
  }
  const civilReg = [
    "Monsieur",
    "Madame",
    "Mademoiselle"
  ]
</script>

<svelte:window on:keydown={handleKey} />

<section class="mx-center">
  <p>
    <!-- Livre d'Or Aloe44.com
    <br> -->
    Merci de nous faire parvenir vos témoignages / anecdotes !
    <br>
    Connectez-vous à <a href={loginUrl} target="_blank" >Google</a> pour enregistrer votre progression. (<a href="https://myaccount.google.com/?hl=fr&nlr=1" target="_blank" >en savoir plus</a>)
    <!-- <br> -->
  </p>
</section>
<section>
  <Form on:submit={submitForm} >
      <Fields legend="Identité">
        <Select name="civil" label="Civilité" bind:value={title} options={civilReg} />
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
