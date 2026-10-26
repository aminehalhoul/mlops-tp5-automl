# Modele manuel ou modele AutoML ? (TP05)

| Critere                    | Manuel (rf 500/16)                                   | AutoML (FLAML 90 s)                                      |
|----------------------------|------------------------------------------------------|----------------------------------------------------------|
| Famille de modele          | foret aleatoire                                      | xgboost                                                  |
| F1 sur le jeu de test      | 0.8669                                               | 0.8582                                                   |
| Temps de recherche machine | 1.6 s (entrainement)                                 | 90.3 s                                                   |
| Temps humain (estimation)  | 45 min                                               | 5 min                                                    |
| Latence mediane (ms)       | 79.7 / 78.7                                          | 16.6 / 16.4                                              |
| Latence p95 (ms)           | 105.5 / 105.9                                        | 31.1 / 28.3                                              |
| Taille du fichier (Mo)     | TAILLE_MANUEL                                        | TAILLE_AUTOML                                            |
| Explicabilite              | Importance des variables, 500 arbres de profondeur 16 : difficile a inspecter | Importance des variables, 333 arbres peu profonds (max_leaves = 4), reglages visibles dans les cfg_ du run MLflow |

## Decision (5 lignes) : quel modele mettre en production, et pourquoi ?

Je mets en production le modele AutoML (xgboost).
Son F1 (0.8582) est a moins d'un point du modele manuel (0.8669).
Sa latence est environ 5 fois plus faible (16 ms contre 79 ms en mediane).
Son fichier est plus petit (TAILLE_AUTOML Mo contre TAILLE_MANUEL Mo), utile pour Docker.
Le cout : 90 s de recherche machine, mais tres peu de temps humain.