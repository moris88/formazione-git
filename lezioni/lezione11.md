# Lezione 11 - I rami (branch)

I rami (branch o più estesamente "ramificazioni") vengono utilizzati in Git per l'implementazione di funzionalità tra loro isolate, cioè sviluppate in modo indipendente l'una dall'altra ma a partire dalla medesima radice. Strutturalmente il ramo predefinito di un progetto gestito tramite il DVCS è il master che viene generato quando si crea un repository; sarà poi possibile ricorrere ad ulteriori diramazioni dedicate a features differenti per poi inserirle nel master, tramite procedura di merging, quando complete.

## Cosa sono in rami in Git

Si ipotizzi di dover lavorare ad un progetto specifico come per esempio la documentazione a corredo di un software. Una volta completata la bozza iniziale quest'ultima dovrà passare il vaglio della revisione per poter essere approvata e pubblicata. Se lo sviluppo dell'applicazione rimane attivo nel tempo si presenterà certamente l'esigenza di effettuare degli aggiornamenti anche a carico della documentazione.

Non sempre però le necessità di aggiornamento si presentano dopo che la revisione della prima bozza viene completata. Motivo per il quale si potrebbe avere l'esigenza di disporre di una versione modificata con i nuovi dati, pur conservando quanto prodotto fino a quando sono stati apportati i cambiamenti richiesti dall'evoluzione del progetto in corso. In sostanza si avranno due versioni distinte della medesima bozza.

E' possibile comprendere meglio il funzionamento di questo meccanismo facendo riferimento alle procedure utilizzate da Git per l'archiviazione delle informazioni, si ricordi infatti che l'applicazione non è stata concepita per memorizzare dati sulla base delle modifiche che hanno subito, ma per salvarli come degli snapshot (istantanee) disposti in sequenza. Si pensi per esempio alla dinamica dei commit, nel momento in cui ne viene eseguito uno verrà generato un oggetto omonimo che punta allo snapshot del contenuto allocato.

I puntatori dei commit rivelano una disposizione gerarchica per la quale il commit iniziale non avrà alcun commit genitore, come accade per il master che è il ramo originario generato di default, un commit successivo avrà un solo genitore (quello iniziale), mentre il commit risultate dal merging di più diramazioni avrà anche più genitori.

## Il ruolo dei puntatori

I puntatori dei commit sono in grado di indicare la posizione di un commit all'interno della cronologia dei commit, in particolare permettono di identificare il commit corrente e i commit genitori. I puntatori dei commit sono utilizzati per navigare nella cronologia dei commit e per identificare i commit associati a un determinato ramo.

I puntatori dei commit sono rappresentati da una serie di caratteri alfanumerici che identificano univocamente un commit all'interno del repository. I puntatori dei commit sono utilizzati per riferirsi ai commit in modo conciso e preciso, in particolare vengono utilizzati per identificare i commit associati a un determinato ramo.

## Creazione di un nuovo ramo

Per creare un nuovo ramo in Git, è possibile utilizzare il comando `git branch`. Il comando `git branch` consente di creare un nuovo ramo a partire dal commit corrente. È possibile specificare un nome per il nuovo ramo utilizzando l'opzione `-b`.

Ad esempio, per creare un nuovo ramo chiamato `feature`:

```bash
git branch feature
```

Questo comando creerà un nuovo ramo chiamato `feature` a partire dal commit corrente.

Con `git branch` Git terrà traccia delle istantanee e del loro ordine risalendo la catena dei commit, utilizzerà poi un proprio puntatore (HEAD) per capire su quale ramo si sta attualmente lavorando. L'utilizzatore dovrà spostarsi volontariamente su un nuovo ramo dopo averlo generato, git branch infatti ne permette la creazione ma non effettua automaticamente il reindirizzamento ad esso.

Il comando che permette ad HEAD di puntare su un nuovo ramo reindirizzando su di esso anche l'utente è `git checkout` seguito dal nome del ramo stesso:

```bash
git checkout feature
```

Si ipotizzi ora di effettuare un nuovo commit, per esempio dopo aver modificato il file README del progetto sul quale si sta lavorando:

```bash
git checkout -b feature
echo "Nuova feature" >> README.md
git add README.md
git commit -m "Aggiunta nuova feature"
```

A differenza di quanto accade con `git branch` il commit sposterà in avanti il ramo a cui punta HEAD, nel caso specifico il ramo newbranch avanzerà di una posizione mentre master punterà comunque al commit nel quale ci si trovava prima del precedente `git checkout`. Lanciando quindi:

```bash
git checkout master
```

HEAD arretrerà fino a puntare su master e i file presenti nella directory di lavoro saranno quelli associati a quest'ultimo e non presenteranno le modifiche eseguite per i nuovi rami; in sostanza, facendo riferimento all'esempio proposto in precedenza, il progetto potrà essere implementato in modo differente rispetto alla direzione che era stata decisa nel momento in cui è stato aggiunto il ramo newbranch.

Ne consegue che, dato che ora il puntatore di Git si trova su master, un eventuale nuovo branch che dovesse essere creato da questa posizione sarà indipendente e parallelo a newbranch fino a quando l'utilizzatore non dovesse optare per una fusione.
