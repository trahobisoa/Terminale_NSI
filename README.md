# Terminale NSI — site de cours (VitePress)

## Installation locale

```bash
npm install
npm run docs:dev
```
Le site est alors accessible sur http://localhost:5173

## Build de production

```bash
npm run docs:build
npm run docs:preview
```

## Déploiement sur GitHub Pages

1. Pousse ce dossier sur la branche `main` de ton repo `Terminale_NSI`.
2. Dans GitHub : **Settings → Pages → Build and deployment → Source : GitHub Actions**.
3. Le workflow `.github/workflows/deploy.yml` se déclenche automatiquement à chaque `push` sur `main` et publie le site.
4. Ton site sera disponible à l'adresse : `https://trahobisoa.github.io/Terminale_NSI/`

⚠️ Vérifie bien la valeur de `base` dans `docs/.vitepress/config.mts` : elle doit correspondre exactement au nom de ton repo (avec les slashes de début/fin), sinon les liens et assets seront cassés une fois déployés.

## Structure

```
docs/
  .vitepress/
    config.mts       # config du site, nav, sidebar
  index.md            # page d'accueil
  cours/
    01-types-construits/
      index.md
    02-bases-donnees/
      index.md
    ...
```

## Ajouter un nouveau cours

1. Convertis ton PDF en Markdown (demande-le à Claude !).
2. Colle le fichier `.md` dans le sous-dossier du chapitre correspondant dans `docs/cours/`.
3. Ajoute l'entrée correspondante dans la `sidebar` de `docs/.vitepress/config.mts`.
4. `git add`, `git commit`, `git push` → le site se met à jour automatiquement.
