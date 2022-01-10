# Normes pour les données d'offres de transport
Le contenu des normes présentes sur le site https://normes.transport.data.gouv.fr (en ligne d'ici fin janvier 2022).

## Structure
Chaque dossier correspond à une norme et contient un fichier `index.md` ainsi qu'un dossier `media` contenant les images présentes dans la page.

## Déploiement
La mise en ligne de ces fichiers se fait via un site statique, généré par [Hugo](https://gohugo.io/) et dont le code est [ici](https://github.com/etalab/transport-normes-site).

## Historique
La rédaction de ces normes a eu lieu pendant plusieurs années sur des documents word, le suivi des modifications étant fait en utilisant l'outil du même nom sur Word. Ces documents Word étaient mis à disposition sur la page http://www.normes-donnees-tc.org/profils/. Afin de garder une tracabilité maximale sur le contenu des fichiers, le dossier `originaux` contient les documents Word (.doc) qui ont servi à la conversion vers le format Markdown (.md) dorénant utilisé.

## Conversion .doc -> .md
Ces étapes ont permis la conversion des fichiers .doc vers les .md correspondants.
Il pourra être utile de s'y référer par la suite pour la conversion de nouveaux documents.

### Sur Word
* Ouvrir le fichier .doc à convertir
* Faire `Fichier > Informations > Vérifier l'absence de problèmes > inspecter le document`
* Supprimer les commentaires, les révisions, les versions, **le texte masqué**
* Faire `Enregistrer sous` et convertir le document en `.docx`
* Supprimer manuellement le sommaire (qui est régénéra par le générateur de site)
* fermer le fichier sur Word

## Modifier le .zip
* renommer le .docx en .zip
* ouvrir l'archive
* ouvir le fichier `/word/document.xml`
* remplacer toutes les occurences de `<w:highlight w:val="lightGray"/>` par `<w:shd w:fill="C0C0C0" w:val="clear"/>`
* Sauvegarder le fichier et mettre à jour l'archive zip avec.

### LibreOffice prend le relais
LibreOffice présente l'avantage de pouvoir sélectionner un texte qui est surligné d'une certaine couleur.
* Faire `Edit > Find and replace` (Ctrl + H)
  * Mettre dans find : `.*`, Replace : `<span class="hl">&</span>`
  * Cocher la case `Regular Expressions`
  * Faire Format... > Highlighting > Color > et mettre  `c0c0c0` comme valeur Hex de couleur, cliquer sur Ok
  * Cliquer sur `Replace All`

### Conversion avec Pandoc
* installer [Pandoc](https://pandoc.org/installing.html)
* Dans un terminal, entrer `pandoc -t gfm --extract-media ./md/norme_xxx/ -o ./md/norme_xxx/index.md norme_xxx.docx`, ce qui aura pour conséquence de créer un dossier `md/norme_xxx` contanant la conversion de `norme_xxx.docx` en markdown et en images dans le dossier media.

### Edition du markdown
- Ajouter en tête au fichier index.md, en prenant modèle sur les autres normes.
- Passer `Avant propos` et `Introduction` en gras (pas en H1, pour garder la numérotation inchangée)
- Remplacer les `\<span` par `<span` et les `\</span` par `</span`
- Remplacer les `&lt;` par `<` et les `&gt;` par `>`
- Si certaines images du dossier `media` ne sont pas en JPEG ou en PNG, les convertir (en faisant une copie d'écran si on ne peut pas faire mieux)
- Remplacer les balises du style `<img src="./md/arrets//media/image1.png" style="width:4.54583in;height:4.18264in" />` par `![image](media/image1.png)` et mettre la légende juste en dessous en italique (entourés de \*) pour que la numérotation automatique des images se fasse.
- Partie `termes et définitions` : mettre en ordre les parties, supprimer la numérotation manuelle.
- Supprimer les numérotations manuelles des tables, et entourer les légendes des tables de `<div class="table-title"> ... </div>` pour que celles-ci soient numérotées automatiquement.
- supprimer les mises en italiques (les `*) des légendes des tables
- changer `gris` en `jaune` dans le texte qui explique ce que signifie le texte surligné.
- supprimer tous les `<!-- -->`

