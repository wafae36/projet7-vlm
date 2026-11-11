# Projet 7 : VLMs légers pour légender ou juger des images

Projet réalisé par Wafae, Meriem et Fatima.

## Le projet

On compare deux petits modèles vision-langage, Qwen2-VL-2B et SmolVLM, sur les mêmes images tirées de Flickr8k. Chaque modèle est testé en précision normale (16 bits), puis quantifié en 8 bits et en 4 bits, pour voir ce qu'on gagne en mémoire et ce qu'on perd en qualité.

On s'en sert de deux façons :

- **Légender les images.** On compare les légendes produites à celles écrites par des humains, puis on garde les meilleures pour constituer un jeu de données qui pourra servir à entraîner une LoRA.
- **Juger des légendes.** Le modèle donne une note de 1 à 5, et on regarde si ses notes rejoignent les nôtres.

Le projet se termine par une petite démo : on charge une image et on obtient une légende ou un score, en choisissant le niveau de quantification.

## Organisation

On travaille semaine par semaine. Chaque dossier contient le notebook de chacune pour la semaine, les résultats obtenus et un court point d'avancement.

| Semaine | Wafae | Meriem | Fatima |
|---|---|---|---|
| [Semaine 1](semaine1_11-16nov) (11 au 16 nov.) | Préparation des images, premier test en 16, 8 et 4 bits | Mise en place et vérification des métriques | Prompt du juge, paires à noter, outil d'annotation |
| [Semaine 2](semaine2_17-23nov) (17 au 23 nov.) | Légendes des six configurations, mémoire et vitesse | Scores de qualité des six configurations | Annotation et notes du juge |
| [Semaine 3](semaine3_24-30nov) (24 au 30 nov.) | Analyse du coût de la quantification | Graphiques de qualité et exemples | Corrélation entre le juge et nos notes |
| [Semaine 4](semaine4_01-07dec) (1er au 7 déc.) | Notebook final | Jeu de données pour la LoRA | Démo Gradio |

## Lancer un notebook

Les notebooks tournent sur Google Colab avec un GPU T4 (*Exécution → Modifier le type d'exécution*). Les images et les résultats intermédiaires sont stockés dans un dossier Google Drive partagé entre nous trois, `projet7_vlm`. Seuls les notebooks et les petits fichiers de résultats sont mis sur GitHub.

Pour que nos résultats restent comparables, on garde toutes les mêmes réglages : `SEED = 42`, `N_IMAGES = 300` et `MAX_SIDE = 512`.
