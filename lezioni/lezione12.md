# Lezione 12 - Rami e merging

Uno dei vantaggi derivanti dal versioning riguarda la possibilità di operare sui vari stadi evolutivi di un progetto indipendentemente dallo status associato all'ultima istantanea disponibile sul relativo repository. A questo proposito si ipotizzi di essere impegnati nello sviluppo di un'applicazione, quest'ultima potrebbe essere in fase avanzata di implementazione e aver già raggiunto la versione stabile 1.0. Volendo introdurre ulteriori funzionalità, magari degne di una nuova major release, potrebbe rivelarsi opportuno creare un nuovo ramo, ad esempio il 2.x.

A questo punto il ramo 1.x non verrà necessariamente abbandonato, anzi, essendo plausibilmente il branch di produzione principale in attesa che la versione 2.0 diventi definitiva, esso continuerà a ricevere supporto. Questo significa che anche nel caso in cui si stia lavorando sul nuovo ramo sarà sempre possibile intervenire su quello precedente nel caso in cui emergano delle problematiche a suo carico.

Potrebbe per esempio accadere che un utilizzatore della release 1.x invii un feedback segnalando l'individuazione di una vulnerabilità o di un malfunzionamento; ricevuta tale notifica gli sviluppatori potranno riprendere in mano la versione buggata, generare un nuovo ramo contenente la correzione del problema rilevato e unire quest'ultimo con quello da correggere per poi tornare a lavorare sul ramo 2.x.

La procedura che prevede l'apertura di un nuovo ramo per l'esecuzione di un intervento e la sua successiva fusione con il ramo che presenta la necessità di un aggiornamento prende il nome di merging, letteralmente "fusione".

## Creazione di un nuovo ramo

Per creare un nuovo ramo in Git, è possibile utilizzare il comando `git branch`. Il comando `git branch` consente di creare un nuovo ramo a partire dal commit corrente. È possibile specificare un nome per il nuovo ramo utilizzando l'opzione `-b`.

Ad esempio, per creare un nuovo ramo chiamato `feature`:

```bash
git checkout -b feature
```

Questo comando creerà un nuovo ramo chiamato `feature` a partire dal commit corrente.

Per completezza, è bene precisare che sarebbe stato possibile ottenere lo stesso risultato digitando le seguenti istruzioni:

```bash
git branch feature
git checkout feature
```

## Merging di un ramo

Per unire due rami in Git, è possibile utilizzare il comando `git merge`. Il comando `git merge` consente di unire due rami, in particolare unisce il ramo specificato al ramo corrente.

Ad esempio, per unire il ramo `feature` al ramo `master`:

```bash
git checkout master
git merge feature
```

Questo comando unirà il ramo `feature` al ramo `master`.
