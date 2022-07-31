<script>
  import Head from "$lib/components/Head.svelte";
  import InputField from "$lib/components/Form/InputField.svelte";
  let firstname = ""
  let lastname = ""
  let phone = ""
  let email = ""
  let way = ""
  let zip = ""
  let cityname = ""
  // let firstname = ""
  // let firstname = ""
  // let firstname = ""
  // let firstname = ""
</script>

<Head title="Livre d'or" />

<div>
  <p>
    Livre d'Or Aloe44.com
Merci de nous faire parvenir vos témoignages / Anecdotes !
Connectez-vous à Google pour enregistrer votre progression. En savoir plus
*Obligatoire
Monsieur
Madame
  </p>
</div>
<section>
  <form action="">
    <fieldset>
      <legend>Identité</legend>
      <InputField bind:value={firstname} label="Prénom" name="firstname" />
      <InputField bind:value={lastname} label="Nom" name="lastname" />
      <InputField bind:value={phone} label="Téléphone" name="phone" entryType="tel" />
      <InputField bind:value={email} label="Adresse courriel" name="email" entryType="email" />
      
      <!-- <div>
        <label for="">Prénom <sup>*</sup></label>
        <input type="text">
      </div>
      <div>
        <label for="">Nom <sup>*</sup></label>
        <input type="text">
      </div>
    -->
    <!-- <div>
      <label for="">Téléphone</label>
      <input type="text">
    </div>
    <div>
      <label for="">Adresse courriel <sup>*</sup></label>
      <input type="text">
    </div> -->
  </fieldset>
  <!-- <fieldset>
    <legend>Coordonnées géographiques</legend>
      <InputField bind:value={way} label="Rue"  name="way" />
      <InputField bind:value={zip} label="Code Postal" name="zip" />
      <InputField bind:value={cityname} label="Ville"  name="cityname" />

 <div>
        <label for="">Rue</label>
        <input type="text">
      </div>
      <div>
        <label for="">Code postal</label>
        <input type="text">
      </div>
      <div>
        <label for="">Ville</label>
        <input type="text">
      </div> 
      </fieldset>
    -->
      <fieldset>
        <legend>Commentaire</legend>
      <div>
        <label for="">Description <sup>*</sup></label>
        <textarea type="text" />
      </div>

    </fieldset>

    
  </form>
</section>
