# hicks-law-conversion

[Read in English](README.md)

Un skill Claude qui audite et conçoit les parcours de SaaS et de sites web pour réduire le nombre de décisions à prendre avant l'achat. Il applique la loi de Hick, la recherche sur la surcharge de choix, les options par défaut et la divulgation progressive à quatre parcours : pages de tarifs, landing pages et CTA, checkout et formulaires, onboarding SaaS.

Il produit des analyses et des specs de pages, pas de code, donc il marche avec n'importe quelle stack.

## Ce qu'il fait

**Mode audit.** Tu lui donnes une capture, une URL, un parcours ou une description. Il recense chaque décision que le visiteur doit prendre, calcule la charge décisionnelle, classe chaque option (garder, fusionner, mettre par défaut, reporter, supprimer), vérifie le tout contre les dark patterns et rend un rapport priorisé avec un plan de test.

**Mode conception.** Tu décris la page ou le parcours voulu. Il rend une spec avec une action principale, l'ordre des sections, les décisions demandées dans chaque section, un wireframe texte, les options par défaut, ce qui est reporté et comment mesurer le résultat.

## Pourquoi un skill de plus

La plupart des skills qui citent la loi de Hick la résument à « moins d'options, c'est mieux ». La recherche ne dit pas ça.

- La loi de Hick est logarithmique et a été mesurée sur des tâches de réaction simples. Elle dit peu de chose des longues listes ou des achats réfléchis.
- La surcharge de choix n'apparaît que dans certaines conditions (options complexes, tâche difficile, acheteur qui ne sait pas ce qu'il veut, envie de décider vite). Deux méta-analyses (Scheibehenne 2010, Chernev 2015) ne sont d'accord sur presque rien d'autre.
- Une bonne partie des statistiques de conversion qui circulent ne renvoient à aucune étude.

Le skill part de là. Il réduit les décisions, pas l'information. Il note chaque chiffre qu'il pourrait citer (de A à D) et refuse de citer ceux qui sont introuvables. Il bloque aussi les tactiques qui convertissent aujourd'hui et coûtent demain en remboursements, en churn et en amendes : add-ons payants précochés, faux badges « le plus populaire », prix qui gonflent à la dernière étape.

## Installation

**Claude Code**

```bash
git clone https://github.com/iPS017/hick-s-law.git
cp -r hick-s-law/hicks-law-conversion ~/.claude/skills/
```

Ou copie le dossier `hicks-law-conversion/` dans `.claude/skills/` à l'intérieur d'un projet.

**Applications Claude**

Zippe le dossier `hicks-law-conversion/` (celui qui contient `SKILL.md`) et importe-le depuis la section Skills des paramètres de Claude.

## Utilisation

Le skill se déclenche tout seul sur des demandes comme :

- « Audite notre page de tarifs, la conversion vers le payant plafonne à 1 % »
- « On a quatre boutons dans le hero, lequel garder ? »
- « Raccourcis ce checkout »
- « Conçois l'onboarding de l'essai gratuit de notre app de facturation »
- « Est-ce que cette page souffre de surcharge de choix ? »

Le skill est rédigé en anglais, mais il répond dans la langue de la demande.

## Structure

```
hicks-law-conversion/
  SKILL.md                 workflow, modes, règles
  reference/
    principles.md          Hick-Hyman, surcharge de choix, défauts, leurre, divulgation
    pricing.md             pages de tarifs et choix d'offre
    landing-cta.md         landing pages, CTA, navigation
    checkout-forms.md      checkout, formulaires, paiement et livraison
    onboarding.md          onboarding SaaS et activation
    ethics.md              architecture de choix vs dark patterns, repères UE
    evidence.md            niveaux de preuve et chiffres à ne pas citer
    templates.md           rapport d'audit, spec de page, exemple complet
evals/
  evals.json               scénarios de test
```

## Tests

`evals/evals.json` contient quatre scénarios (audit de tarifs, conception de landing page, demande de dark pattern, audit d'onboarding en français) avec le comportement attendu. Lance-les avec et sans le skill et compare.

## Limites

- Le score en « bits » sert à comparer une page avant et après un changement. Il ne prédit ni un temps ni une conversion.
- Les recommandations restent des hypothèses tant qu'elles ne sont pas testées sur ton trafic.
- La partie juridique donne des repères, pas un avis juridique.

## Licence

MIT
