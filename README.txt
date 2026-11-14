MY BUDGET — VERSION 9

Application de budget personnel, installable comme PWA et utilisable hors connexion après le premier chargement.

MISE À JOUR
1. Décompressez l'archive.
2. Remplacez les fichiers à la racine de votre dépôt GitHub Pages par les fichiers de cette archive.
3. Conservez la même adresse GitHub Pages et ne supprimez pas les données du navigateur.
4. Rechargez le site. Si l'ancienne version reste affichée, fermez complètement l'application puis rouvrez-la ; le service worker utilise un nouveau cache.

DONNÉES ET MIGRATION
- Les données restent stockées localement dans le navigateur (localStorage, clé mybudget_v1).
- La migration depuis les versions précédentes conserve le profil, les dépenses fixes, les dépenses mobiles, les salaires et les mouvements d'épargne déjà enregistrés.
- Les dates de salaire et de dépenses sont supprimées conformément au nouveau fonctionnement. La date réelle des remboursements de crédit est conservée et ne peut pas être postérieure à la date du jour.
- Avant toute mise à jour importante, exportez une sauvegarde depuis Paramètres.

FONCTIONNEMENT
- Après l'initialisation, choisissez vous-même le mois de référence. Les mois proposés vont de janvier 2020 au mois réel autorisé par le calendrier ; le mois suivant n'apparaît que pendant la dernière semaine du mois réel.
- Tous les onglets suivent le mois consulté. Le bouton de retour ramène au mois de référence.
- Les mois clôturés restent modifiables via « Modifier ce mois ». Les soldes concernés sont recalculés.
- Les dépenses fixes intégrées et personnalisées sont gérées dans Paramètres ; chaque mois conserve ses propres montants. Les dépenses ponctuelles sont appelées « Dépenses mobiles ».
- Les contributions d'épargne sont définies une seule fois par mois. Le solde cumulé est calculé selon les mois, retraits et remboursements. Pour répartir les retraits entre les origines, les contributions les plus anciennes sont utilisées en premier.
- Les crédits restent visibles de leur mois de création jusqu'au mois de leur remboursement complet. Les remboursements peuvent provenir de l'épargne cumulée ou du solde d'un mois déterminé. Un remboursement est rattaché au mois consulté, tandis que sa date réelle est conservée séparément.
- Les fiches mensuelles et bilans annuels PDF sont générés localement.

PROTECTION
- Le PIN ou mot de passe est facultatif, proposé pendant l'initialisation et modifiable/supprimable dans Paramètres.
- Le secret est stocké sous forme de dérivé PBKDF2 salé dans le stockage local. C'est un verrou d'accès local, pas un chiffrement complet des données.
