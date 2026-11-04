# Portal Rush — Audit technique et feuille de route

Date : 4 novembre 2026. Branche de travail : `dev/portal-rush-3d`.

## État vérifié du code
- `index.html` : jeu autonome HTML/CSS/JavaScript, rendu avec Canvas 2D ; pas de moteur 3D identifié.
- Écran d'accueil : portail animé, visuel de menu et vidéo `portal-intro.mp4` référencés dans le code.
- Jeu : quatre biomes (Dimension Toxique, Forêt Cristalline, Désert Zarbi, Glacier Néon), déplacements, dash, armes, ennemis, bots, boss et boss ultimes.
- Progression : expérience, quêtes, monnaie interne, boutique, skins, pass et sauvegarde locale (`localStorage`).
- Le bouton « multijoueur » indique explicitement que le véritable multijoueur n'est pas encore disponible ; les adversaires actuels sont des bots.
- Le code ne référence actuellement aucun fichier `.glb`, `.gltf`, `.fbx` ou `.obj`. Les dossiers d'assets 3D doivent être inventoriés et leurs licences vérifiées avant intégration.

## Objectif produit
Préserver le jeu 2D original comme mode **Portal Arcade** ; créer séparément **Portal Adventure** en 3D et, plus tard, **Portal City** comme hub reliant Arcade, Adventure, Race, Arena, Survival et Tycoon.

## Plan d'exécution
1. Sauvegarder le fonctionnement actuel ; extraire le jeu Canvas dans un chemin Arcade sans changement de comportement.
2. Inventorier les assets 3D réellement présents (formats, taille, textures, animations, licences, compatibilité web).
3. Prototyper une scène 3D légère : caméra troisième personne, personnage, déplacement, collisions, environnement, portail.
4. Construire progressivement Portal Adventure à partir de ce prototype.
5. Ajouter Portal City et la navigation entre modes.
6. Implémenter ensuite le multijoueur avec serveur, comptes et sauvegarde sécurisée.
7. Réexaminer la monétisation, la progression gratuite et le Portal Pass avant tout paiement réel.

## Garde-fous
- Ne jamais écraser `main` sans tests et validation.
- Préserver les sauvegardes existantes du jeu original.
- Ne pas présenter les bots comme du multijoueur réel.
- Ne pas considérer les achats affichés dans le code comme des paiements fonctionnels.
- Vérifier les droits d'utilisation des assets avant publication.
