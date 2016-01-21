# Compétition de parallélisme

## Auteur

- Julien Zakaib (VP-Compétitions)
- Lucas Bajolet (VP-Compétitions)
- Philippe Pépos Petitclerc (VP-Président)
- Romain Chanoir (VP-Lore)
- N/A (Professeur Collaborateur)

## Mise en contexte

//Todo

## Description

Vous devez implémenter un algorithme parallèle d’un automate cellulaire, soit un jeu de la vie. 

### Définition

Ceci consiste en la création d’un algorithme qui gère la vie de cellules à l’intérieur d’une matrice. Une cellule peut donc être sous deux état soit en vie ou défunte, selon les conditions énoncé plus bas.

### Condition de vie

1. Une cellule qui n’a pas au moins deux voisins meurt.
2. Une cellule qui a 2 ou 3 voisins vivra pour une génération de plus.
3. Une cellule avec plus de 3 voisins meurt
4. Une cellule morte avec exactement 3 voisins reprend vie.

### Précision

Chacune des conditions doit être vérifié pour chaque cellules individuelles avant de passé à la prochaine génération.

### Exemple

Une ligne de 3 cercles effectuera une rotation sur son point centrale, les extrémités changeant leurs localisation selon les conditions de vie précisé plus haut.
//Todo: Inserer image

## Langages autorisé 

C et C++

### Thread C

int pthread_create(pthread_t *restrict thread, 
const pthread_attr_t *restrict attr, void *(*start_routine)(void*), 
void *restrict arg);

### Mutex C

int pthread_mutex_init(pthread_mutex_t *restrict mutex, 
const pthread_mutexattr_t *restrict attr);

int pthread_mutex_lock(pthread_mutex_t *mutex);

### Thread C++

std::thread leThread (foo);

### Mutex C++

lock();

Unlock();

## Durée
3 heures