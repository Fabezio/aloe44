<script>
  import Head from "$lib/components/Head.svelte";
  import Fields from "$lib/components/Form/Fields.svelte";
  import Form from "$lib/components/Form/Form.svelte";
  import InputField from "$lib/components/Form/InputField.svelte";
  import TextareaField from "$lib/components/Form/TextareaField.svelte";
  let firstname = ""
  let lastname = ""
  let phone = ""
  let email = ""
  let way = ""
  let zip = ""
  let cityname = ""
  let message = ""
  let data = []
  function handleKey (e) {
    if (e.key === "Enter") {
      submitForm()
    }
  }
  function submitForm () {
    const newUser = {
      firstname: firstname,
      lastname: lastname,
      phone: phone,
      email: email,
      way: way,
      zip: zip,
      cityname: cityname,
      message: message
    }
    data = [...data, newUser]
    console.log(data)
    firstname = ""
lastname = ""
phone = ""
email = ""
way = ""
zip = ""
cityname = ""
message = ""

    return data
  }
  </script>
<Head title="Contactez-moi !" />
<svelte:window on:keydown={handleKey} />
<div>
  <p>
    Conformément à la loi, en tant que VDI, les tarifs sont absents du site afin de préserver les droits du consommateur.
    <br>
    <br>
    
    Commandez maintenant vos produits directement en ligne.
    <br>
    Envoyez nous votre adresse mail et postale à contact@aloe44.com
    <br>
    Vous recevrez un code client pour vous connecter sur le site de commande en ligne !
    <!-- <br>
      06.82.21.91.24
      <br>
      02.40.49.69.33 -->
    </p>
  </div>
  <section>
    <Form on:submit={submitForm} >
      <Fields legend="Identité">
        <InputField bind:value={firstname} label="Prénom" name="firstname" />
        <InputField bind:value={lastname} label="Nom" name="lastname" />
        <InputField bind:value={phone} label="Téléphone" name="phone" entryType="tel" />
        <InputField bind:value={email} label="Adresse courriel" name="email" entryType="email" />
      </Fields>
      
      <Fields legend="Coordonnées géographiques" >
        <InputField bind:value={way} label="Rue"  name="way" />
        <InputField bind:value={zip} label="Code Postal" name="zip" />
        <InputField bind:value={cityname} label="Ville"  name="cityname" />
      </Fields>

      <Fields legend="Commentaire" >
        <TextareaField label="Message" name="message" bind:value={message} />
      </Fields>
      
    </Form>
    <br />
    {#if data.length}
    <pre>
      {JSON.stringify(data, null, 2)}
  </pre>

  {/if} 
</section>
