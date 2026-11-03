# Lords Shield — prototype Android

## Ce que contient cette version
- Écran Android avec les réglages demandés :
  - alerte espion activée (configuration prototype)
  - réaction à un ralliement activée (configuration prototype)
  - réaction à une attaque entrante activée (configuration prototype)
  - durée préférée du bouclier : 24 heures
  - achats de bouclier avec gemmes : interdits
- Journal local en mémoire et bouton de simulation.
- Workflow GitHub Actions pour compiler un APK debug dans le cloud.

## Limite essentielle
Ceci est uniquement un prototype d'interface. Il ne capture pas l'écran, ne détecte pas réellement les attaques et ne clique pas dans Lords Mobile. Ne comptez pas sur cette version pour protéger un compte. La détection et l'activation automatiques nécessitent une conception et des tests supplémentaires, des autorisations Android explicites et une vérification réelle de l'interface du jeu. Les actions en jeu lorsque l'écran est verrouillé ne sont pas garanties.

## Compiler depuis le téléphone sans ordinateur (méthode cloud)
1. Téléchargez ce ZIP sur votre téléphone et décompressez-le.
2. Dans le navigateur, connectez-vous à GitHub et créez un nouveau dépôt vide nommé `LordsShield` (ne cochez pas l'option pour ajouter un README).
3. Utilisez l'interface Web de GitHub pour téléverser les fichiers et dossiers de ce projet en conservant leur structure. Si le navigateur mobile ne permet pas de téléverser plusieurs fichiers, activez « Version pour ordinateur » ou téléversez les fichiers par petits groupes.
4. Une fois les fichiers dans la branche `main`, ouvrez l'onglet **Actions** du dépôt.
5. Choisissez **Build Lords Shield APK** puis **Run workflow** si le workflow ne s'est pas lancé automatiquement.
6. Lorsque le workflow est terminé avec succès, ouvrez son exécution, faites défiler jusqu'à **Artifacts**, puis téléchargez `LordsShield-debug-apk`.
7. Décompressez l'artefact téléchargé : il contient `app-debug.apk`. Ouvrez ce fichier sur le téléphone et autorisez l'installation depuis cette source si Android le demande.

## Compiler directement sur Android
Un IDE Android sur téléphone peut aussi compiler des projets Gradle, mais certains IDE mobiles historiques ne sont plus maintenus. Vérifiez le statut et la source officielle avant d'installer un IDE. La compilation dans le cloud est la voie de départ la plus simple pour ce projet.

## Détails techniques
- Kotlin
- minSdk 26
- compileSdk 35
- targetSdk 35
- applicationId `ca.lordsshield.prototype`

L'APK debug est destinée aux tests et n'est pas une publication Play Store.
