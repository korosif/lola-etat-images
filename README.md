# Lola — État des illustrations

Petit tableau de suivi des 72 illustrations de *Une lapine sur la lune*.

## Architecture

- **`main/index.html`** : interface GitHub Pages, accessible depuis PC et iPhone.
- **`data/etat_images.json`** : seul fichier de suivi opérationnel, avec historique Git.
- Les identifiants d’illustration restent stables ; les titres, pages, formats et étapes sont modifiables.
- Pas de dépendance à Apps Script / Google Drive pour le fonctionnement quotidien.

## Mise en ligne

1. Pour GitHub Free, rendre ce dépôt **public** dans **Settings → General → Danger Zone → Change repository visibility**. Sur une offre permettant Pages depuis un dépôt privé, ce changement n’est pas nécessaire, mais les sites Pages restent publiquement accessibles selon les paramètres GitHub.
2. Dans **Settings → Pages**, sélectionner **Deploy from a branch**, branche **main**, dossier **/(root)**, puis **Save**.
3. Ouvrir l’URL Pages affichée dans ces réglages, normalement `https://korosif.github.io/lola-etat-images/`.

## Activer la sauvegarde

Dans GitHub, créer un **fine-grained personal access token** sur le compte `korosif`, limité au dépôt `lola-etat-images` uniquement, avec **Repository permissions → Contents → Read and write**.

Dans l’application, utiliser **Accès GitHub**, coller le jeton, puis **Connecter et charger**. À répéter sur chaque appareil. Ne jamais publier le jeton dans le dépôt, une capture d’écran ou une conversation. L’option « Mémoriser sur cet appareil » conserve le jeton dans le navigateur (à éviter sur ordinateur partagé) ; sinon, il ne persiste que pour l’onglet/la session.

Une case cochée déclenche un commit sur `data`. L’interface recharge la dernière version avant chaque écriture et réessaie en cas de conflit SHA ; si un même champ a été modifié ailleurs, elle refuse d’écraser silencieusement la valeur concurrente.

## Contrôle initial

1. Vérifier la présence des huit chapitres et des 72 illustrations.
2. Cocher « Recherche » sur une illustration : attendre « Synchronisé avec GitHub ».
3. Recharger la page : la coche doit rester visible.
4. Vérifier la présence d’un commit récent dans la branche `data`.
5. Vérifier sur iPhone puis sur PC.

## Précautions

- Les statuts de validation sont indépendants et ne sont jamais déduits automatiquement d’autres étapes.
- Titres/pages issus du storyboard V1.1, et certains formats estimés, restent provisoires.
- Si le dépôt est public, le JSON et son historique sont **publics**. Le jeton n’est jamais intégré à l’HTML.
- Pour sauvegarder plus tard sur Drive, exporter le fichier `data/etat_images.json`. Ne pas réinitialiser la branche `data` depuis l’ancienne copie Drive.
