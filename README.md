# MF PROTECH — Formulaire de découverte

Formulaire de qualification client pour Marietou Fall / MF PROTECH.

## Déployer sur Vercel en 3 étapes

### Étape 1 — Crée un compte Vercel
Va sur https://vercel.com → "Sign up" → connecte avec GitHub

### Étape 2 — Upload le projet
**Option A — Via GitHub (recommandé)**
1. Crée un repo GitHub (privé ou public)
2. Upload les fichiers `index.html` et `vercel.json`
3. Sur Vercel → "Add New Project" → importe le repo
4. Clique "Deploy" → c'est live en 30 secondes

**Option B — Via Vercel CLI**
```bash
npm i -g vercel
cd mfprotech-form
vercel
```

### Étape 3 — Personnalise le domaine
Dans Vercel Dashboard → Settings → Domains
→ Change le nom en : `mfprotech-formulaire.vercel.app`
→ Ou connecte un domaine custom si t'en as un

## Lien à envoyer à Marietou
```
https://mfprotech-formulaire.vercel.app
```

## Récupérer les réponses
Pour l'instant les réponses s'affichent dans la console du navigateur (F12).
Pour les recevoir par email ou les stocker → intègre Formspree ou Netlify Forms.

### Intégrer Formspree (gratuit, 50 soumissions/mois)
1. Va sur https://formspree.io → crée un compte
2. Crée un nouveau form → copie ton endpoint (ex: `https://formspree.io/f/xabcdef`)
3. Dans `index.html`, dans la fonction `nextStep()` au moment du submit final, ajoute :

```javascript
fetch('https://formspree.io/f/TONID', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify(answers)
});
```

→ Tu reçois les réponses par email à chaque soumission.
