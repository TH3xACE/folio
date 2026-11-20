# Folio — Personal Budget Manager

Folio is a lightweight personal finance app for tracking income, expenses, and savings. It runs in the browser and stores account and budget data in that browser's local storage.  It is designed to be easy to use for non-IT users, without requiring any local server setup.

![Folio dashboard screenshot](docs/screenshots/dashboard.png)

> Dashboard capture.

## Features

- Personal accounts with sign-in, sign-up, and sign-out.
- Admin console for creating users, resetting passwords, and deleting accounts.
- Separate admin category manager. Categories are grouped by expense, income, or saving and can be added or deleted.
- Monthly overview with income, expense, savings, balance, recent transactions, and a category spending breakdown.
- Month navigation, including past and future months, for reviewing and entering transactions.
- Transaction management for income, expense, and saving entries, with categories, saving sub-categories, and platforms such as PEA and CTO.
- Savings goals and contributions.
- Recurring transaction templates.
- Cash-flow, savings, and annual report charts, including year-to-year comparisons. Hover over charts for value labels.
- Monthly and annual CSV exports.
- Household profiles for family members and relationships.
- Light, Dark, Ocean, Lavender, and Sunset themes.
- English and French language selection.
- EUR, GBP, and USD currency display.
- Responsive layout for desktop and mobile screens.

## Getting started

1. Download or clone this repository.
2. Open `index.html` in a modern browser.
3. Sign in with one of the built-in accounts below.

No build step or package installation is required.

## Default accounts

| Role | Username | Password |
| --- | --- | --- |
| Administrator | `admin` | `admin` |
| Demo user | `user1` | `user1` |

NOTE: Connect as admin and change the default passwords.

The built-in credentials are for local demonstration only. Accounts and finance data are stored locally in the browser and are not synchronized between devices.

## Screenshots

Add screenshots to `docs/screenshots/` and update the image paths below.

### Dashboard

![Dashboard](docs/screenshots/dashboard.png)

### Annual report

![Annual report](docs/screenshots/annual-report.png)

### Manage users

![Manage users](docs/screenshots/manage-users.png)

## Language

Choose **English** or **French** from the language selector in the top bar. The selected language is saved with the signed-in account and used for the interface labels and date formatting.

## Currency

Choose **EUR**, **GBP**, or **USD** from the currency selector. Amounts in the interface and CSV exports use the selected currency display. Currency selection changes formatting only; it does not convert transaction amounts between currencies.

## Themes

Choose **Light**, **Dark**, **Ocean**, **Lavender**, or **Sunset** in Settings. Theme choice is saved per account. The cash-flow and savings charts, spending pie chart, and chart legends use coordinated colors for the active theme.

## Future improvements

Monthly budgets per category: 
- set a limit for Food or Housing and show progress bars, with a warning at 80% and 100%.
- Auto-apply recurring entries: apply them automatically at the start of each month, with a preview before confirming. Today it’s a manual “Apply to month” click.
- Forecast: project end-of-month balance from recurring entries plus your average spending, and show it as a dotted line on the cash flow chart.
- Goal deadlines: add a target date to each savings goal and show the monthly amount needed to reach it, with a “behind or on track” label.

Savings and investments

- Portfolio view by platform: the PEA, CTO, Assurance-vie and Livret A breakdown could show allocation percentages and, if you enter market value, gains or losses.
- Savings rate trend: a line chart of savings as a percentage of income, plus a simple “months of expenses saved” emergency-fund indicator.
- Contribution handling: goal contributions currently always book to the “Emergency fund” category. Letting you pick the category and platform would keep the platform table accurate.

Insights

- Month-over-month comparison: show “Food is up 18% vs last month” and flag unusual spikes.
- Search and filters: search by text, amount range, category and date range on the Transactions page, with sorting.
- Top expenses and trends: a category trend chart over 6 or 12 months, and a “biggest expenses” list.
- Household split: tag transactions to a household member and compare or split shared costs.

Data and usability

- CSV and bank import: import statements with automatic category suggestions based on past descriptions (for example, “Carrefour” → Food).
- Edit transactions: there’s currently only delete, so add editing and bulk actions.
- Backup and restore: export and import the full data as JSON. This matters most, since everything lives in localStorage and clearing the browser wipes it.
- Multi-currency: store each transaction’s currency, with conversion at the time you entered it, instead of just changing the display format.
- PDF annual report: a printable summary from the Reports page.

Technical, for when it grows

- Real backend and password hashing
- PWA: make it installable and usable offline on a phone.
- Reminders: notifications for bills due, budget limits and goal milestones.

An online version:
- Replace browser-local accounts with a secure server-side authentication and database service.
- Add encrypted backups, data import, and cross-device synchronization.
- Support additional currencies, locale formats, and optional exchange-rate conversion.
- Use of AI to assist and provide advice on how to improve budget.


## For DEV - Adding languages, currencies, and themes

Folio is currently a single-file app. Its interface, settings, and chart palette are defined in `index.html`.

- **Add a language:** add the language code and translated labels to the `T` translation dictionary, add an option to the language selectors, and verify date formatting for that locale.
- **Add a currency:** add the ISO currency code to both currency selectors and make sure `fmt()` formats it with `Intl.NumberFormat`. Currency conversion is not included; adding it would require exchange-rate data and conversion rules.
- **Add a theme:** add a theme option to Settings, add its color variables and body class in the stylesheet, and add a coordinated entry to `THEME_PALETTES` for income, expenses, savings, and pie slices.
- **Add a screenshot:** save the image under `docs/screenshots/` and update the corresponding Markdown image path above.


## Fonctionnalités (français)

Folio est une application de gestion de budget personnel pour suivre les revenus, les dépenses et l’épargne. Elle fonctionne dans le navigateur et conserve les comptes et les données financières dans le stockage local du navigateur. Il est conçu pour être facilement utilisable par des personnes non spécialisées en informatique, sans nécessiter l'installation ni l'hébergement d'un serveur local.

- Comptes personnels avec connexion, inscription et déconnexion.
- Console d’administration pour créer des utilisateurs, réinitialiser les mots de passe et supprimer des comptes.
- Gestion séparée des catégories, classées par dépenses, revenus ou épargne.
- Vue mensuelle avec revenus, dépenses, épargne, solde, transactions récentes et répartition des dépenses par catégorie.
- Navigation entre les mois passés et futurs pour consulter ou saisir des transactions.
- Transactions de revenus, dépenses et épargne, avec catégories, sous-catégories d’épargne et plateformes telles que PEA et CTO.
- Objectifs d’épargne et contributions.
- Modèles de transactions récurrentes.
- Graphiques de flux de trésorerie, d’épargne et rapports annuels, avec comparaison entre années. Survolez les graphiques pour afficher les valeurs.
- Export CSV mensuel et annuel.
- Profil du foyer avec les membres de la famille et leurs relations.
- Thèmes Clair, Sombre, Océan, Lavande et Coucher de soleil.
- Interface en français et en anglais.
- Affichage des montants en EUR, GBP et USD.
- Interface adaptée aux ordinateurs et aux mobiles.

## Installation

1. Téléchargez ou clonez ce dépôt.
2. Ouvrez `index.html` dans un navigateur récent.
3. Connectez-vous avec l’un des comptes prédéfinis ci-dessus.

Aucune compilation ni installation de dépendances n’est nécessaire.

Les identifiants prédéfinis sont réservés à la démonstration locale. Les comptes et les données budgétaires restent dans le stockage local du navigateur et ne sont pas synchronisés entre appareils.

## Budgets mensuels par catégorie

- **Budgets mensuels par catégorie :** définir un plafond pour l'alimentation ou le logement et afficher des barres de progression, avec une alerte à 80 % et à 100 % du budget.
- **Application automatique des opérations récurrentes :** appliquer automatiquement les opérations récurrentes au début de chaque mois, avec un aperçu avant validation. Actuellement, cette opération nécessite un clic manuel sur « Appliquer au mois ».
- **Prévisions budgétaires :** estimer le solde à la fin du mois en tenant compte des opérations récurrentes et des dépenses moyennes, puis afficher cette prévision sous forme de ligne pointillée sur le graphique des flux de trésorerie.
- **Échéances des objectifs :** ajouter une date cible à chaque objectif d'épargne et afficher le montant mensuel nécessaire pour l'atteindre, accompagné d'un indicateur précisant si l'objectif est « en bonne voie » ou « en retard ».

## Épargne et investissements

- **Vue du portefeuille par plateforme :** présenter la répartition du PEA, du CTO, de l'assurance-vie et du Livret A, avec les pourcentages d'allocation et, si la valeur de marché est renseignée, les gains ou les pertes.
- **Évolution du taux d'épargne :** afficher un graphique en courbes représentant le pourcentage des revenus consacré à l'épargne, ainsi qu'un indicateur simple du nombre de mois de dépenses couverts par le fonds d'urgence.
- **Gestion des versements :** actuellement, les versements destinés aux objectifs sont systématiquement affectés à la catégorie « Fonds d'urgence ». Permettre de sélectionner la catégorie et la plateforme concernées afin de maintenir une vue précise des différents placements.

## Analyses et indicateurs

- **Comparaison mensuelle :** afficher des comparaisons telles que « Les dépenses alimentaires ont augmenté de 18 % par rapport au mois dernier » et signaler les hausses inhabituelles.
- **Recherche et filtres :** ajouter une fonction de recherche par texte, montant, catégorie et période dans la page des transactions, avec possibilité de trier les résultats.
- **Principales dépenses et tendances :** intégrer un graphique d'évolution des dépenses par catégorie sur 6 ou 12 mois, ainsi qu'une liste des dépenses les plus importantes.
- **Répartition des dépenses du foyer :** permettre d'associer chaque transaction à un membre du foyer afin de comparer ou de répartir les dépenses communes.

## Données et ergonomie

- **Import CSV et relevés bancaires :** permettre l'importation de relevés bancaires avec suggestion automatique de catégories à partir des libellés des transactions précédentes (par exemple, « Carrefour » → « Alimentation »).
- **Modification des transactions :** actuellement, seule la suppression est possible. Ajouter la modification des transactions ainsi que des actions groupées.
- **Sauvegarde et restauration :** permettre l'exportation et l'importation de l'ensemble des données au format JSON. Cette fonctionnalité est particulièrement importante puisque toutes les données sont actuellement stockées dans le localStorage du navigateur et peuvent être perdues si celui-ci est vidé.
- **Gestion multidevise :** enregistrer la devise de chaque transaction et appliquer le taux de conversion en vigueur au moment de sa saisie, plutôt que de simplement modifier le format d'affichage.
- **Rapport annuel PDF :** générer un rapport annuel imprimable et téléchargeable depuis la page « Rapports ».

## Évolutions techniques (à mesure que l'application se développe)

- **Véritable backend et sécurisation des mots de passe :** mettre en place une architecture backend avec une gestion sécurisée de l'authentification et du stockage des mots de passe.
- **PWA (Progressive Web App) :** rendre l'application installable sur smartphone et utilisable hors ligne.
- **Rappels et notifications :** envoyer des notifications concernant les factures à échéance, les limites budgétaires et les étapes importantes des objectifs d'épargne.

## Version en ligne

- **Authentification et base de données sécurisées :** remplacer les comptes stockés localement dans le navigateur par un système d'authentification côté serveur et une base de données sécurisée.
- **Sauvegardes chiffrées, importation et synchronisation :** mettre en place des sauvegardes chiffrées, faciliter l'importation des données et permettre leur synchronisation entre plusieurs appareils.
- **Prise en charge de plusieurs devises et formats régionaux :** gérer différentes devises, les formats de dates et les paramètres régionaux, avec une conversion des taux de change facultative.
- **Intégration de l'intelligence artificielle :** utiliser l'IA pour analyser les habitudes financières, fournir des conseils personnalisés et proposer des pistes concrètes pour améliorer la gestion du budget.
