# Écoville : mettre le jeu en ligne pour jouer avec les téléphones

Le jeu tient dans un seul fichier, `index.html`. Pour que les téléphones puissent scanner le QR code, ce fichier doit être accessible sur une adresse publique en `https://`.

## Option simple : GitHub Pages (gratuit)

1. Créer un compte sur github.com.
2. Créer un dépôt public, par exemple `ecoville`.
3. Y déposer `index.html` (bouton « Add file » puis « Upload files »).
4. Aller dans Settings → Pages → Branch : `main` → Save.
5. Après 1 à 2 minutes, le jeu est en ligne sur `https://<ton-pseudo>.github.io/ecoville/`.

## En classe

1. Ouvrir l'adresse sur l'ordinateur relié au projecteur : c'est l'écran de jeu.
2. Un téléphone par équipe scanne le QR code et choisit son équipe.
3. Lancer la quête.

Si un téléphone n'arrive pas à se connecter (réseau de l'école trop filtré), l'équipe peut annoncer sa réponse à voix haute. L'enseignant clique alors sa lettre (A, B, C ou D) à l'écran.

## Comment ça marche

L'écran et les téléphones se parlent directement (WebRTC). Un serveur public gratuit (PeerJS) sert seulement à les mettre en relation. Aucun compte élève n'est nécessaire et aucune donnée n'est stockée.

## Modifier les questions

Les questions sont dans `index.html`, dans le tableau `const Q = [...]`. Chaque ligne contient :
- `k` : le quartier (`dech`, `plast`, `tel`, `ia`, `mode`, `alim`) ;
- `l` : le degré minimum (1 = 1re-2e, 2 = 3e-4e, 3 = 5e-6e) ;
- `t` : le type (`qcm`, `vf` ou `tri`) ;
- `a` : les réponses, la bonne toujours en premier (ou `v: true/false` pour un vrai/faux) ;
- `e` : l'explication montrée à la correction.
