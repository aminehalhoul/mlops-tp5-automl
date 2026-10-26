# Modele manuel ou modele AutoML ? (TP05)

| Critere                    | Manuel (rf 500/16)  | AutoML (FLAML 90 s)       |
|----------------------------|---------------------|---------------------------|
| Famille de modele          | foret aleatoire     | xgboost                   |
| F1 sur le jeu de test      | 0.8669              | 0.8582                    |
| Temps de recherche machine | 1.6 s (entrainement)| 90.3 s                    |
| Temps humain (estimation)  | ... min             | ... min                   |
| Latence mediane (ms)       | 79.7 / 78.7         | 16.6 / 16.4               |
| Latence p95 (ms)           | 105.5 / 105.9       | 31.1 / 28.3               |
| Taille du fichier (Mo)     | ... (a mesurer)     | ... (a mesurer)           |
| Explicabilite              | ...                 | ...                       |

## Decision (5 lignes) : quel modele mettre en production, et pourquoi ?
...