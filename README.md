# Checklist intégration d'emails 🔥⚔️

L'objectif de cette checklist est de regrouper de manière condensée l'essentiel de ce qu'il faut retenir pour réaliser des intégrations d'emails responsive de manière moderne.

Influance(s) menant à cette checklist :

- [FrontEnd Masters Course on html email development V2](https://frontendmasters.com/courses/html-email-v2)

## Petit rappel de ce qui devrait marcher, et ne pas marcher du tout

Ce qui devrait marcher :

- HTML Basique
- CSS basique
  - pour le texte : `color`, `font-family`, `font-size`, `font-style`, `font-weight`, `line-height`, `text-align`
  - pour les blocs : `margin`, `padding`, `width`, `max-width`, `border`
- Layout basé sur les tableaux

Ce qui ne marchera surement pas :

- Positionnement `float`
- CSS Grid
- JavaScript
- Pas mal de CSS

## Starter

Pour bien démarrer, utilisez le fichier `template.html` qui fournira une base solide.

Si jamais vous avez un layout global très simple en une seule colonne, vous pouvez partir du fichier [`single-column-hybrid.html` (lien externe vers un fork du repo de frontend masters)](https://github.com/tidusia/frontendmasters/blob/master/Code%20Examples/Single-Column-Hybrid.html) qui utilise des techniques de _spongy coding_ (inclut des balises spécifiques à Outlook).

Prenez bien garde aux commentaires html inclus à l'intérieur, ils préciseront des points de détails importants qui ne seront pas donnés dans ce document.

## Boutons

Pour les boutons, les 2 meilleures approches sont les suivantes :

- Générer un buton en VML (artillerie lourde) sur [Buttons.cm](https://buttons.cm/)
- Utiliser la solution en example dans le `template.html` qui utilise du `table` + du padding et des bordures

## Images

- Toujours remplir l'attribut alt (sauf pour les éléments purement décoratifs sans aucune sémantique)
- Rester sur les formats traditionnels : `jpg`, `png`, `gif`
- Compresser les images au maximum pour limiter les ressources en bande passante de l'utilisateur
- Pour rendre une image responsive, suivez l'exemple dans le template (`img#responsive-image`)
- Si vous utilisez des background-images, pensez à ajouter une couleur de fond au cas où votre image ne serait pas chargée, comme dans le template (`#background-image`)
- Ne pas utiliser des images pour remplacer du contenu textuel difficile à styliser
- Et bien sur, utilisez des liens absolus (contrairement au template qui utilise les images du repo !)

## Accessibilité côté design

- Contraste de couleur élevé
- Rendre la hierarchie des informations claire au premier coup d'oeil
- La priorité : facilité de lecture (taille de police, espacements, hauteur de ligne, 14px minimum pour tout contenu textuel (oui, même les infos légales, lien de désinscription etc.))
- Autant que possible, conserver le standard visuel pour les liens : couleur différente et souligné. Et en bonus : `font-weight: bold`.
- Limiter le texte centré et justifié, surtout pour les paragraphes
- Limitez l'usage des images, elles sont très souvent bloquées par les clients mails ou les utilisateurs et consomment de la bande passante souvent inutilement. Votre contenu doit être principalement textuel, les images sont un bonus visuel. Un bon exemple d'utilisation d'image est le logo, avec un attribut alt. Un mauvais exemple : une image contenant du texte et des faux boutons.
- Garder une structure simple

## Accessibilité côté développement

- Pour le contenu, vos balises préférées seront `div`, `span`, `h1` à `h6`, `p`, `strong`, `em` et `img`
- Pour la structure et le positionnement, faites la paix avec `table`, oubliez les `thead`, `tbody` et `tfoot`. Place aux `tr` et `td` !
- Ajouter l'attribut `role="presentation"` aux éléments `table`
- Utiliser le `px` pour toutes les unités de mesure
- Ne pas utiliser des images pour les boutons, les liens et le contenu textuel
- L'attribut `lang` est très important. Bien penser à le mettre à jour pour chaque campagne internationnalisée. Si une (ou plusieures) partie distincte de votre document html est dans un autre langage, vous pouvez surcharger la langue localement en appliquant un autre attribut `lang` à cet élément précis.
- Même si la plupart des clients mails ne vont pas utiliser la balise `title`, il est intéressant de l'indiquer quand même car certaines personnes vont ouvrir et trier leurs emails dans un navigateur
- Vous pouvez choisir le texte qui sera utilisé en description d'email (sous la ligne d'objet), il s'agira du premier texte dans le body. Vous pouvez le masquer comme dans le template (`#description`).

## Aller plus loin

Une fois votre email prêt, vous pouvez apporter des améliorations qui, même si elles ne seront pas supportées par tous les clients mails, seront un plus pour l'expérience utilisateur de ceux qui en bénéficieront. Voici le type d'amélioration que vous pouvez mener :

- Changement de styles au `:hover`
- Animations CSS (keyframes)
- Ajouter une [réelle couche d'interactivité](https://www.webdesignerdepot.com/2015/10/punched-card-coding-the-secret-of-interactive-email/) qui peut aller jusqu'à créer un panier d'achat dans le mail, qui pourra être soumis sous la forme d'un formulaire pour compléter l'achat sur le site. Vous pouvez voir un exemple sur le [repo de frontendmasters](https://github.com/rodriguezcommaj/frontendmasters/blob/master/Code%20Examples/Interactivity.html)

## En apprendre plus

- [The Better Email course](https://thebetter.email/design)
- [The Better Email resources directory](https://thebetter.email/resources)
- [The Litmus blog](https://litmus.com/blog/)
- [The Litmus Community](https://litmus.com/community)
- [The Fresh Inbox blog](https://freshinbox.com/blog/)
- [Email Marketing Rules book](http://www.emailmarketingrules.com/email-marketing-rules/)
- [Litmus Live conference](https://litmus.com/conference)
- [Really Good Emails](https://reallygoodemails.com/)
- [Can I email?](https://www.caniemail.com/)
- [Campaign Monitor's Ultimate Guide to CSS](https://www.campaignmonitor.com/css/)

## Ressources intéressantes

- [Litmus tools](https://litmus.com/) : conception, test et analyse des campagnes d'emails
- [Buttons.cm](https://buttons.cm/) : génération de bouttons à toute épreuve (mais code vraiment complexe)
- [Backgrounds.cm](https://backgrounds.cm/)
- [NVDA](https://developer.paciellogroup.com/blog/2008/01/nvda-a-free-and-open-source-screen-reader-for-windows/) : lecteur d'écran pour windows
- [VoiceOver](https://help.apple.com/voiceover/mac/10.15/) : lecteur d'écran pour MacOS
- [NoCoffee](https://chrome.google.com/webstore/detail/nocoffee/jjeeggmbnhckmgdhmgdckeigabjfbddl?hl=en-US) : pour simuler des déficiences visuelles
- [Tota11y](https://khan.github.io/tota11y/) : pour vérifier la structure et la sémantique
- [SilkTide](https://silktide.com/) : pour auditer de nombreux aspects, va beaucoup plus loin que l'a11y
- [WAVE](https://wave.webaim.org/) : outil d'audit a11y
- [Email Client Market Share](http://emailclientmarketshare.com/) : pour savoir quels sont les clients mails les plus utilisés
- [Email Marketing Priorities](https://litmus.com/blog/email-marketing-priorities-and-budget-changes) : étude sur les fonctionnalités les plus demandées par les marketers pour leurs campages d'emails
- [PutsMail](https://putsmail.com/) : pour s'envoyer des emails HTML sans passer par un outil de campagne
- [MJML: Mailjet Markup Language](https://mjml.io/)
- [Foundation for Emails](https://foundation.zurb.com/emails.html)
- [Maizzle email framework](https://maizzle.com/)
- [Campaign Monitor CSS inliner](https://www.campaignmonitor.com/resources/tools/css-inliner/)
- [Mailchimp CSS inliner](https://templates.mailchimp.com/resources/inline-css/)

## Rencontrer les pros de l'email

- [#EmailGeeks Slack channel](https://email.geeks.chat/)
- [The Litmus Community](https://litmus.com/community)
- [Some good people to follow](https://thebetter.email/resources#people)
