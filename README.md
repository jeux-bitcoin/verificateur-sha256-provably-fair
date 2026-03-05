# 🔐 Vérificateur SHA-256 Provably Fair

Un outil open-source pour vérifier l'intégrité des server seeds dans les casinos crypto à équité vérifiable.

**[➡️ Utiliser l'outil en ligne](https://jeux-bitcoin.github.io/verificateur-sha256-provably-fair/)** | **[📖 Comprendre le Provably Fair](https://jeux-bitcoin.com/provably-fair/)**

## À quoi sert cet outil ?

Quand vous jouez sur un casino crypto utilisant le système Provably Fair, le casino vous affiche un **hash du server seed** avant votre mise. Après la partie, le casino vous révèle le server seed en clair.

Cet outil vous permet de vérifier que le hash SHA-256 du seed révélé correspond bien au hash qui vous a été montré avant la partie. Si les deux correspondent, le casino n'a pas changé le seed en cours de route.

## Fonctionnalités

| Fonction | Description | Statut |
|----------|-------------|--------|
| 🔐 Vérification SHA-256 | Vérifiez que le server seed correspond à son hash | ✅ Prêt |
| 🔍 Calcul HMAC-SHA256 | Recalculez le résultat à partir des seeds et du nonce | ✅ Prêt |
| 📋 Comparaison de hash | Collez le hash affiché par le casino pour comparer | ✅ Prêt |

## Comment l'utiliser

### En ligne
Ouvrez l'**[outil en ligne](https://jeux-bitcoin.github.io/verificateur-sha256-provably-fair/)** dans votre navigateur. Aucune installation nécessaire.

### En local
1. Clonez ce dépôt : `git clone https://github.com/jeux-bitcoin/verificateur-sha256-provably-fair.git`
2. Ouvrez `index.html` dans votre navigateur
3. Entrez vos données et cliquez sur Vérifier

## Comment fonctionne la vérification

1. Avant votre mise, le casino affiche un **hash du server seed** (empreinte SHA-256)
2. Vous placez votre mise avec votre propre **client seed** et un **nonce** (compteur de mises)
3. Après la partie, le casino révèle le **server seed en clair**
4. Vous pouvez alors vérifier deux choses :
   - Le hash SHA-256 du seed révélé correspond au hash affiché avant la mise
   - Le résultat HMAC-SHA256 des trois paramètres donne bien le résultat de votre partie

## Détails techniques

La vérification repose sur deux opérations cryptographiques standard :

1. **SHA-256** pour vérifier l'intégrité du server seed (le casino ne l'a pas changé)
2. **HMAC-SHA256** pour recalculer le résultat de la partie à partir du server seed, du client seed et du nonce

Ces algorithmes sont les mêmes que ceux utilisés par le réseau Bitcoin pour sécuriser les transactions.

## Ressources

- [Provably Fair : le guide complet](https://jeux-bitcoin.com/provably-fair/) — Explication détaillée en français
- [Les meilleurs casinos Bitcoin](https://jeux-bitcoin.com/) — Casinos testés par notre équipe
- [HMAC-SHA256 — Wikipédia](https://fr.wikipedia.org/wiki/HMAC)

## Contribuer

Les contributions sont les bienvenues. Si vous souhaitez ajouter une fonctionnalité ou corriger un bug, ouvrez une pull request.

## Licence

Licence MIT — voir le fichier [LICENSE](LICENSE) pour les détails.

---

Développé et maintenu par [Jeux-Bitcoin.com](https://jeux-bitcoin.com) — Guide indépendant des casinos crypto en français
