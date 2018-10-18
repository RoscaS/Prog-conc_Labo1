# Programmation concurrente: Labo1

* **Date**: 17/10/2018
* **Élèves**: Kneuss Michael, Latino Nathan, Rosca Sol
* **Classe**: INF2b
* **Échéance**: 23/10/2018

## Rapport

### Usage

`gcc -pthread main.c -o main [number of threads] [increments/thread]`
* number of threads: `int`
* increments/thread: `int`


## Consigne

### Objectifs
* Prise en main des threads POSIX
* Réalisation d’un programme utilisant la librairie Pthread
* Comparaison de resultats selon differentes aproches

### Cahier des charges

Coder un programme qui effectue une simple incrémentation d’une variable compteur un certain nombre de fois. Le programme va créer M : thread qui vont chacune incrémenter N : fois la variable compteur (Ex : pour M et N : 10’000). Si vous le lancez et le compilez, vous devriez observer des valeurs étranges pour la valeur finale du compteur. Vous devez pouvoir entrer au clavier M et N. et en sortie lorsque tous les threads sont terminés vous devez afficher la valeur finale du compteur ainsi que le ratio (valeur finale observée/valeur finale attendue). Faites le même programme plusieurs fois :
* Une fois sans système de blocage
* Une fois avec de l’attente active (Verrouillage)

```
While (verrou != 0)
    //Attente active
    End while
    Verrou <- 1
    Section_critique();
    Verrou <- 0
```
* Une fois avec sched_yield(void)
* Une fois avec pthread_mutex_t

Trouver la méthode qui donne la meilleur la valeur finale et pourquoi ?
Durant vos essais, vous pouvez jeter aussi un oeil et tester d’autres méthodes :

* Instruction de barrière mémoire : __asm__ volatile ("mfence":::"memory");
* (Sous QT) : QThread::yieldCurrentThread().
* (Microsoft Visual Studio) _ReadWriteBarrier();

