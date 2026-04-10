# Moodify
 
Moodify est une application web qui analyse les émotions à partir d'images et propose une playlist Spotify adaptée.
 
## Fonctionnalités
 
* Télécharger une image pour analyser les émotions.
* Afficher l'émotion détectée et le niveau de confiance.
* Obtenir une playlist Spotify adaptée à l'émotion détectée.
* Interface utilisateur interactive et responsive.
 
## Prérequis
 
Pour lancer Moodify, assurez-vous d'avoir installé :
 
* Python 3.8+
* pip (gestionnaire de paquets Python)
* MongoDB (pour stocker les émotions et les entrées)
 
## Instructions d'installation
 
### 1. Cloner le dépôt
 
```bash
git clone <repository-url>
cd Moodify
```
 
### 2. Installer les dépendances
 
```bash
pip install python-dotenv flask flask-cors google-genai pymongo
```
 
### 3. Configurer MongoDB
 
Assurez-vous que MongoDB est en cours d'exécution localement ou à distance. Mettez à jour la chaîne de connexion à la base de données dans `app.py` si nécessaire.
 
> **Avant de démarrer**, contactez **Hanine** pour configurer MongoDB et obtenir les accès à la base de données.
 
### 4. Lancer l'application
 
Démarrez le serveur Flask :
 
```bash
python app.py
```
 
L'application sera disponible à l'adresse `http://127.0.0.1:5000`.
 
### 5. Accéder à l'interface web
 
Ouvrez votre navigateur et rendez-vous sur :
 
```
http://127.0.0.1:5000
```
 
## Structure du projet
 
```
Moodify/
│   ├── app.py               # Backend Flask
│   ├── static/              # Fichiers statiques (CSS, JS)
│   │   ├── style.css        # Styles de l'application
│   │   ├── script.js        # Logique frontend
│   ├── templates/           # Templates HTML
│   │   ├── index.html       # Page d'accueil
│   │   ├── playlist.html    # Page de playlist
│   ├── README.md            # Documentation du projet
│   ├── emotions.json        # Données d'émotions (exemples)
│   ├── entries.json         # Données d'entrées (exemples)
```
 
## Problèmes connus
 
* L'application plante occasionnellement.
* Les entrées ne sont plus sauvegardées en base de données.
* La fonctionnalité d'analyse par IA n'est pas opérationnelle.
 
## Endpoints API
 
### 1. `/analyse-emotion` (POST)
 
* **Description** : Accepte une image et retourne l'émotion détectée ainsi que le niveau de confiance.
* **Requête** :
  * Méthode : `POST`
  * Corps : `FormData` contenant un fichier image.
* **Réponse** :
 
```json
{
  "emotion": "happy",
  "confidence": 95.0
}
```
 
### 2. `/save-emotion` (POST)
 
* **Description** : Sauvegarde l'émotion détectée et l'URL de la playlist Spotify associée.
* **Requête** :
  * Méthode : `POST`
  * Corps : JSON avec `emotion` et `spotify_url`.
* **Réponse** :
 
```json
{
  "message": "Emotion enregistrée avec succès"
}
```
 
### 3. `/playlist` (GET)
 
* **Description** : Affiche la dernière émotion détectée et sa playlist Spotify.
* **Réponse** : Rendu du template `playlist.html`.
 
## Licence
 
Ce projet est sous licence MIT. Consultez le fichier `LICENSE` pour plus de détails.
 
## Remerciements
 
* **Flask** pour le framework backend.
* **MongoDB** pour la base de données.
* **Spotify** pour les playlists.
* Les bibliothèques et outils open-source utilisés.
