
<template>
  <!-- Conteneur principal -->
  <div class="container">
    <h2>Login</h2>

    <!-- Formulaire avec prévention du rechargement -->
    <form @submit.prevent="login">

      <!-- Champ email lié à la variable email -->
      <input 
        type="email" 
        v-model="email" 
        placeholder="Enter email" 
      />

      <!-- Champ mot de passe lié à la variable password -->
      <input 
        type="password" 
        v-model="password" 
        placeholder="Enter password" 
      />

      <!-- Bouton de soumission -->
      <button type="submit">Login</button>
    </form>

    <!-- Message affiché après action -->
    <p v-if="message">{{ message }}</p>
  </div>
</template>

<script>
export default {
  // Données du composant
  data() {
    return {
      email: "",       // stocke l'email saisi
      password: "",    // stocke le mot de passe saisi
      message: ""      // message affiché à l'utilisateur
    }
  },

  // Méthodes du composant
  methods: {
    login() {

      // Vérifie si les champs sont vides
      if (!this.email || !this.password) {
        this.message = "All fields are required";
        return;
      }

      // Identifiants simulés (fake)
      const correctEmail = "admin@test.com";
      const correctPassword = "1234";

      // Vérification des identifiants
      if (this.email === correctEmail && this.password === correctPassword) {
        this.message = "Login successful ";
      } else {
        this.message = "Invalid credentials ";
      }
    }
  }
}
</script>

<style>
/* Style du conteneur */
.container {
  width: 300px;
  margin: auto;
  text-align: center;
}

/* Style des champs */
input {
  display: block;
  margin: 10px auto;
  padding: 8px;
  width: 90%;
}

/* Style du bouton */
button {
  padding: 8px 15px;
}
/* Centrer toute la page */
body {
  background: linear-gradient(135deg, #667eea, #764ba2);
  font-family: Arial, sans-serif;
}

/* Conteneur principal */
.container {
  width: 350px;
  margin: 100px auto;
  padding: 30px;
  border-radius: 12px;
  background: white;
  box-shadow: 0 8px 20px rgba(0,0,0,0.2);
  text-align: center;
}

/* Titre */
h2 {
  margin-bottom: 20px;
  color: #333;
}

/* Champs input */
input {
  display: block;
  width: 100%;
  margin: 12px 0;
  padding: 10px;
  border-radius: 8px;
  border: 1px solid #ccc;
  transition: 0.3s;
}

/* Effet focus */
input:focus {
  border-color: #667eea;
  outline: none;
}

/* Bouton */
button {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
  background: #667eea;
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 16px;
  cursor: pointer;
  transition: 0.3s;
}

/* Hover bouton */
button:hover {
  background: #5a67d8;
}

/* Message */
p {
  margin-top: 15px;
  font-weight: bold;
}

/* Message succès */
p:contains("successful") {
  color: green;
}

/* Message erreur */
p:contains("Invalid"),
p:contains("required") {
  color: red;
}
</style>