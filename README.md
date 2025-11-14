# My Croquette Factory

Une application web élégante et autonome pour calculer la portion quotidienne de croquettes à donner à votre chien.

## Fonctionnalités
- Calcul automatique de la ration à partir du poids du chien et de la densité énergétique des croquettes (kcal/100 g).
- Sauvegarde locale des paramètres via le `localStorage` pour éviter de tout ressaisir.
- Interface responsive, sans dépendances externes (HTML, CSS et JavaScript purement embarqués).
- Contrôles numériques customisés pour ajuster facilement les valeurs.

## Formule utilisée
```
110 × (poids en kg)^0.75 ÷ (kcal pour 100 g) × 100 = portion quotidienne (en grammes)
```

La portion quotidienne est également proposée en deux repas égaux pour une distribution plus simple.

## Comment l'utiliser
1. Ouvrez `index.html` dans votre navigateur.
2. Renseignez le poids de votre chien (en kg) et la valeur énergétique de vos croquettes (kcal pour 100 g).
3. La portion recommandée s'affiche automatiquement. Les valeurs seront mémorisées pour votre prochaine visite.

## Stack
- HTML5
- CSS3 (styles inline, design glassmorphism)
- JavaScript vanilla (calculs + persistance locale)

## Auteur
Projet conçu pour faciliter la vie des maîtres soucieux de l'alimentation de leur compagnon. Bonne utilisation !
