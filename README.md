# Freedom
Best version of YouTube 

<!DOCTYPE html>
<html>
<head>
  <title>FreedomVid</title>
  <style> body { font-family: sans-serif; text-align: center; } video { margin: 20px auto; display: block; } </style>
</head>
<body>
  <h1>FreedomVid</h1>
  <p>Upload ta vidéo. Libre.</p>
  
  <input type="file" id="vid" accept="video/*">
  <button onclick="checkAndPlay()">Envoyer</button>

  <video id="player" controls></video>

  <div id="statut">Prêt.</div>

  <script>
    function checkAndPlay() {
      const file = document.getElementById('vid').files[0];
      const statut = document.getElementById('statut');
      
      if (!file) { statut.innerText = "Choisis une vidéo d'abord."; return; }

      statut.innerText = "IA vérifie... (c'est bidon hein)";

      setTimeout(() => {
        // Ici, en vrai, t'appellerais une API
        statut.innerText = "Vérifié. C'est bon.";
        const url = URL.createObjectURL(file);
        document.getElementById('player').src = url;
      }, 1200);
    }
  </script>
</body>
</html>
