# optimisation-de-portefeuille-gestion-des-erreurs-


# **1. Simulation de portefeuilles statistiquement équivalents**

## 1.1 Librairies<a id="2.1"></a>

numpy-pandas-matplotlib-cvxpy

## 1.2 Fonction pour calculer portefeuille optimal
Minimiser la variance pour un rendement cible




L’optimisation de portefeuille moderne (Markowitz, 1952) vise à déterminer la composition d’un portefeuille qui **minimise le risque** (mesuré par la variance ou l’écart-type des rendements) pour un **niveau donné de rendement attendu**.

On considère \( n \) actifs, avec :

$$
\boldsymbol{\mu} \in \mathbb{R}^n \quad \text{: vecteur des rendements espérés}
$$

$$
\Sigma \in \mathbb{R}^{n \times n} \quad \text{: matrice de covariance des rendements}
$$

$$
\boldsymbol{w} \in \mathbb{R}^n \quad \text{: vecteur des poids du portefeuille}
$$

avec la contrainte de somme des poids :

$$
\sum_{i=1}^n w_i = 1
$$

---



On cherche à minimiser le risque :

$$
\min_{\boldsymbol{w}} \quad \boldsymbol{w}^\top \Sigma \boldsymbol{w}
$$

Sous les contraintes suivantes :

$$
\boldsymbol{w}^\top \boldsymbol{1} = 1
$$

$$
\boldsymbol{w}^\top \boldsymbol{\mu} = \mu_p
$$

$$
\boldsymbol{w} \geq \boldsymbol{0}
$$

où :

𝜇𝑝 est le rendement cible du portefeuille,


1 est un vecteur colonne de 1 de dimension 
𝑛
,


w≥0 impose qu’aucune vente à découvert n’est autorisée (contraintes de positivité des poids).

La frontière efficiente correspond à l’ensemble des portefeuilles optimaux pour chaque valeur possible de 
𝜇
𝑝

​
 . Elle représente le compromis optimal entre rendement espéré et risque.


## 1.3 Data

Simuler un jeu de données financier


## 1.4 Portefeuille optimal et Bootstrap


# **2. Estimation de la frontière efficiente resamplée**


L’idée : on calcule la moyenne des portefeuilles optimaux obtenus sur plusieurs échantillons bootstrap — cela stabilise la frontière et limite l’impact des erreurs d’estimation.

# **3. Estimation bootstrap de la frontière efficiente complète**

Ici, on génère plusieurs points de rendement cible et on applique la procédure bootstrap sur chacun pour estimer une frontière efficiente "resamplée".





