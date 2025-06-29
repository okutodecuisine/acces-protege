<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Accès protégé</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      text-align: center;
      padding: 100px 20px;
    }
    #secret {
      display: none;
      margin-top: 30px;
      background: #dff0d8;
      padding: 20px;
      border-radius: 10px;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
    }
  </style>
</head>
<body>

  <h1>🔐 Accès sécurisé</h1>
  <p>Veuillez entrer le code d'accès :</p>

  <input type="text" id="codeInput" placeholder="Code d'accès" />
  <button onclick="checkCode()">Valider</button>

  <div id="secret">
    <h2>✅ Accès autorisé</h2>
    <p>Voici votre lien privé : <a href="https://meet.brevo.com/breth-robert " target="_blank">Cliquez ici</a></p>
  </div>

  <script>
    function checkCode() {
      const code = document.getElementById("codeInput").value.trim();
      const authorizedCode = "brethvip";

      if (code === authorizedCode) {
        document.getElementById("secret").style.display = "block";
      } else {
        alert("❌ Code incorrect");
      }
    }
  </script>

</body>
</html>
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Protégée</title>
  <style>
    /* Style de la modale */
    .modal {
      display: none; /* Cachée par défaut */
      position: fixed;
      z-index: 1; /* Au-dessus du contenu */
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      overflow: auto;
      background-color: rgb(0,0,0); /* Foncé */
      background-color: rgba(0,0,0,0.4); /* Avec transparence */
    }

    .modal-content {
      background-color: #fff;
      margin: 15% auto;
      padding: 20px;
      border: 1px solid #888;
      width: 300px;
      text-align: center;
    }

    /* Le bouton de fermeture */
    .close {
      color: #aaa;
      float: right;
      font-size: 28px;
      font-weight: bold;
    }

    .close:hover,
    .close:focus {
      color: black;
      text-decoration: none;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <!-- Bouton pour ouvrir la modale -->
  <button id="openModalBtn">Renseigner votre e-mail</button>

  <!-- La modale -->
  <div id="emailModal" class="modal">
    <div class="modal-content">
      <span class="close">&times;</span>
      <h2>Entrez votre adresse e-mail</h2>
      <form id="emailForm">
        <input type="email" id="email" placeholder="Votre e-mail" required>
        <button type="submit">Envoyer</button>
      </form>
    </div>
  </div>

  <script>
    // Obtenir les éléments nécessaires
    var modal = document.getElementById("emailModal");
    var btn = document.getElementById("openModalBtn");
    var span = document.getElementsByClassName("close")[0];

    // Ouvrir la modale
    btn.onclick = function() {
      modal.style.display = "block";
    }

    // Fermer la modale quand l'utilisateur clique sur la croix
    span.onclick = function() {
      modal.style.display = "none";
    }

    // Fermer la modale si l'utilisateur clique en dehors de celle-ci
    window.onclick = function(event) {
      if (event.target == modal) {
        modal.style.display = "none";
      }
    }

    // Soumettre le formulaire et envoyer l'e-mail (simple logique ici)
    document.getElementById("emailForm").addEventListener("submit", function(event) {
      event.preventDefault(); // Empêche la soumission par défaut

      var email = document.getElementById("email").value;
      if (email) {
        alert("L'e-mail suivant a été soumis : " + email);
        // Ici tu peux rajouter la logique pour envoyer cet e-mail à un serveur ou à un service comme Make, EmailJS, etc.
        modal.style.display = "none"; // Ferme la modale après soumission
      } else {
        alert("Veuillez entrer un e-mail valide.");
      }
    });
  </script>

</body>
</html>
