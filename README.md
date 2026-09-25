# SHOPPTON-G68 — version avec administration sécurisée

Cette version permet de gérer depuis `/admin.html` :
- produits, catégories, prix, formats et visibilité
- emoji et URL d'image
- nom de la boutique
- contact Telegram
- texte d'accueil
- secteur de livraison

## Important
GitHub Pages est un hébergement statique. Il ne faut PAS mettre un mot de passe admin directement dans le HTML.
Cette version utilise Supabase Auth + Row Level Security (RLS).

## Mise en place
1. Crée un projet Supabase.
2. Dans SQL Editor, exécute `supabase-schema.sql`.
3. Dans Authentication > Users, crée ton compte administrateur avec email + mot de passe.
4. Récupère l'UUID de cet utilisateur et exécute la ligne `insert into public.profiles...` indiquée à la fin du SQL.
5. Dans Supabase > Project Settings > API, récupère :
   - Project URL
   - Publishable/anon key
6. Ouvre `admin.html` et remplace :
   `TON_SUPABASE_URL`
   `TON_SUPABASE_ANON_KEY`
7. Mets `index.html`, `admin.html` et `supabase-schema.sql` dans ton dépôt GitHub.
8. Ouvre `https://TON-SITE/admin.html` pour administrer la boutique.

Ne mets JAMAIS la `service_role` key dans GitHub ou dans `admin.html`.
