<script>
  import Head from "$lib/components/Head.svelte";
  import InputField from "$lib/components/Form/InputField.svelte";
  import TextareaField from "$lib/components/Form/TextareaField.svelte";
  import Button from "$lib/components/Button.svelte";
  let firstname = ""
  let lastname = ""
  let phone = ""
  let email = ""
  let way = ""
  let zip = ""
  let cityname = ""
  let message = ""
  let user
  let data = []
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
    return data
  }
  </script>
<Head title="Contactez-moi !" />
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
    <form action="" on:submit|preventDefault={submitForm} >
    <fieldset>
      <legend>Identité</legend>
      <InputField bind:value={firstname} label="Prénom" name="firstname" />
      <InputField bind:value={lastname} label="Nom" name="lastname" />
      <InputField bind:value={phone} label="Téléphone" name="phone" entryType="tel" />
      <InputField bind:value={email} label="Adresse courriel" name="email" entryType="email" />
      
    </fieldset>
    <fieldset>
      <legend>Coordonnées géographiques</legend>
      <InputField bind:value={way} label="Rue"  name="way" />
      <InputField bind:value={zip} label="Code Postal" name="zip" />
      <InputField bind:value={cityname} label="Ville"  name="cityname" />
      
    </fieldset>
    <fieldset>
      <legend>Commentaire</legend>
      <TextareaField label="Message" name="message" bind:value={message} />
      
      
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
  <!-- {message} -->
  {/if} 
</section>
