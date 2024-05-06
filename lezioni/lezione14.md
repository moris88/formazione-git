# Lezione 14 - Rebasing

Uno tra i comandi più utili in Git è Rebase: vediamone le differenze rispetto al merging e le operazioni che è possibile effettuare con esso.

## Differenze tra rebasing e merging

In Git il rebasing (o rifondazione) è una procedura molto simile al merging che presenta però delle differenze di carattere concettuale oltre a basarsi su comandi diversi. Partendo dalle caratteristiche che accomunano questi due strumenti possiamo affermare che il rebasing, tramite l'istruzione git rebase, svolge la medesima funzionalità del merging attraverso il comando git merge, consente cioè di includere le modifiche eseguite a carico di un ramo in un altro ramo.

Detto questo, è importante sottolineare che il rebasing e il merging assolvono questo compito in modo differente. Si ipotizzi per esempio di essere coinvolti in un progetto collaborativo e di creare un nuovo ramo da dedicare all'introduzione di una feature addizionale, potrebbe succedere che mentre stiamo lavorando all'implementazione di quest'ultima un altro componente del nostro team esegua degli interventi sul ramo master ed effettui dei commit per confermare tali aggiornamenti.

Come potremmo procedere per fare in modo che i commit a carico del master vengano inclusi anche nel ramo generato per sviluppare la nuova feature? Per risolvere questo problema possiamo ricorrere al merging, che già conosciamo, ma il rebasing ci fornisce un'ulteriore alternativa.

## Rebasing dei rami

Il rebasing consente di spostare i commit di un ramo su un altro ramo, in particolare consente di riapplicare i commit di un ramo su un altro ramo. Questo processo consente di mantenere la cronologia dei commit lineare e di evitare la creazione di merge commit.

Ad esempio, per eseguire il rebasing del ramo `feature` sul ramo `master`:

```bash
git checkout feature
git rebase master
```

Questo comando sposterà i commit del ramo `feature` sul ramo `master`.

## Risoluzione dei conflitti

Durante il rebasing potrebbero verificarsi dei conflitti, ad esempio se i commit del ramo `feature` entrano in conflitto con i commit del ramo `master`. In questo caso, è necessario risolvere i conflitti manualmente.

Per risolvere i conflitti durante il rebasing, è possibile utilizzare i comandi `git add` e `git rebase --continue`. Il comando `git add` consente di aggiungere i file risolti al commit, mentre il comando `git rebase --continue` consente di continuare il rebasing dopo aver risolto i conflitti.

Ad esempio, per risolvere i conflitti durante il rebasing:

```bash
git add <file>
git rebase --continue
```

Questi comandi consentono di risolvere i conflitti durante il rebasing e di continuare il processo di riapplicazione dei commit.

## I limiti del rebasing

Il rebasing è un'operazione potente ma va utilizzata con cautela, in particolare è importante considerare i seguenti aspetti:

- Il rebasing modifica la cronologia dei commit, quindi è sconsigliato utilizzarlo su commit già condivisi con altri utenti.
- Il rebasing può causare la perdita di commit nel caso in cui si commettano errori durante il processo.
- Il rebasing può generare conflitti che richiedono risoluzione manuale.

In generale, il rebasing è utile per mantenere una cronologia dei commit lineare e pulita, ma è importante utilizzarlo con attenzione per evitare problemi.

## Rebasing su rami multipli

Il rebasing può essere utilizzato anche su rami multipli, ad esempio per riapplicare i commit di un ramo su un altro ramo. In questo caso, è possibile specificare il ramo di destinazione del rebasing.

Ad esempio, per eseguire il rebasing del ramo `feature` sul ramo `master`:

```bash
git checkout feature
git rebase --onto master feature feature2
```

Traducendo quanto digitato, stiamo in pratica ordinando a Git di prendere il ramo "feature2" considerando soltanto le componenti comuni con "feature" e di procedere all'unione con il master.

## Merging post rebasing

Dopo aver eseguito il rebasing, è possibile procedere con il merging del ramo rebased con un altro ramo. Questo processo consente di includere le modifiche riapplicate nel ramo di destinazione.

Ad esempio, per unire il ramo `feature` rebased al ramo `master`:

```bash
git checkout master
git merge feature
```

Questo comando unirà il ramo `feature` rebased al ramo `master`.

Successivamente al merging, il ramo `feature` rebased sarà stato integrato nel ramo `master` e la cronologia dei commit sarà lineare. Non rimane altro che cancellare i due rami derivati divenuti ormai inutili:

```bash
git branch -d feature
git branch -d feature2
```

Questo comando eliminerà i rami `feature` e `feature2` dal repository locale.

Immaginiamo di inserire una dinamica simile all'interno di un progetto sviluppato da più collaboratori, ognuno impegnato nell'implementazione di una specifica funzionalità. Grazie al rebasing possiamo sincronizzare più flussi di lavoro rispettando la cronologia di tutti i cambiamenti effettuati, senza alcuna sovrapposizione.
