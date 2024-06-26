# Lezione 1 - Che cos'è Git? Perché Git?

## Che cos'è Git?

Git è un sistema di controllo di versione distribuito (DVCS), creato da Linus Torvalds nel 2005. Git è un software libero e open source, distribuito sotto la GNU General Public License versione 2.

## Perché Git?

Git è uno strumento molto potente e flessibile, che permette di tenere traccia delle modifiche ai file di un progetto, permettendo di tornare indietro nel tempo e di collaborare con altre persone.

Git è molto veloce e leggero, e permette di lavorare in locale senza dover essere connessi a internet.

Git è molto diffuso e supportato da una vasta comunità di sviluppatori, che forniscono supporto e risolvono i problemi.

Git è molto flessibile e permette di lavorare con diversi tipi di progetti, da piccoli progetti personali a grandi progetti aziendali.

Git è molto sicuro e permette di tenere traccia delle modifiche ai file, permettendo di recuperare facilmente le versioni precedenti.

Git è molto efficiente e permette di lavorare in modo collaborativo, permettendo a più persone di lavorare sullo stesso progetto contemporaneamente.

## Il controllo di versione

Il controllo di versione (versioning) è sostanzialmente un meccanismo attraverso il quale tenere traccia con il passare del tempo delle modifiche apportate ad un progetto; quest'ultimo può essere costituito da un singolo file o da un insieme di file le cui diverse versioni vengono registrate e possono essere richiamate in un momento successivo, anche a grande distanza di tempo, ogni volta che se ne presenti la necessità.

In linea generale, si tende ad associare il concetto di controllo di versione allo sviluppo di applicazioni e all'implementazione delle differenti release, tuttavia è possibile applicare il versionig anche a progetti di natura differente, come per esempio la documentazione relativa ad un sistema o a un linguaggio, le specifiche associate a uno standard, una cronologia, un layout grafico (si pensi per esempio all'evoluzione di un logo), nel complesso, qualsiasi file sia suscettibile di modifiche.

Nello specifico dello sviluppo software, ma il discorso potrebbe essere ampliato ad altri ambiti di utilizzo, l'impiego di un sistema per il controllo di versione consente di semplificare il lavoro di un team, fornendo ai suoi componenti gli strumenti per monitorare i cambiamenti effettuati da terzi ad ogni revisione, per risalire ad un intervento che potrebbe aver causato un malfunzionamento, per annullare una variazione ripristinando la precedente release di un file o di un progetto nel suo insieme.

Esistono diverse modalità per controllo di versione: dal semplice monitoraggio locale a sistemi centralizzati, fino al versioning distribuito proprio di Git. Comprendere le differenze tra questi approcci aiuterà a scegliere quello più adatto per le prorpie esigenze.

## Controllo di versione locale

Il controllo di versione locale è la forma più essenziale e primitiva di versioning; si immagini uno sviluppatore che crea un'applicazione, effettua la presentazione o la messa in produzione di quest'ultima e poi, magari su suggerimento del committente, effettua delle modifiche introducendo aggiornamenti e correzioni. In questo caso le diverse versioni del progetto potrebbero essere salvate in differenti cartelle rinominate, ad esempio associando la data dell'ultima modifica effettuata al nome del progetto.

Almeno in teoria tale approccio non necessita di un software per la gestione delle diverse relese, ma cosa potrebbe accadere nel caso di progetti articolati coinvolti da numerose modifiche? Tenere traccia degli interventi effettuati diventerebbe complesso con il rischio di perdere molte informazioni con il passare del tempo e l'accumularsi degli interventi eseguiti. Ecco perché vennero ideate le prime soluzioni per il versiong come per esempio il free software RCS (Revision Control System), queste ultime funzionano grazie ad un database destinato a registrare le modifiche apportate ai file e tramite delle patch che memorizzano le differenze tra le revisioni in modo da semplificare le operazioni di ripristino.

Sistemi come RCS facilitano il controllo di versione locale ma offrono strumenti limitati per lo sviluppo in ambito collaborativo, motivo per il quale si cercò una soluzione a tale problematica ricorrendo ai CVCS (Centralized Version Control Systems).

## Controllo di versione centralizzato

I sistemi centralizzati per il controllo di versione (chi li adotta conoscerà sicuramente Subversion), sono caratterizzati dal fatto di funzionare sulla base di un singolo server a cui viene affidato il compito di ospitare tutte le varianti dei progetti sottoposti a versioning, tale server permetterà quindi anche il download dei file da parte degli utenti interessati a partecipare allo sviluppo, a creare dei fork (versioni derivate dal sorgente di un progetto originale) o semplicemente ad utilizzare una determinata applicazione.

Tali sistemi offrono degli indubbi vantaggi rispetto a quelli per il controllo di versione locale, soprattutto in considerazione del fatto che in un contesto che prevede la partecipazione di più soggetti sarà più facile tenere traccia delle modifiche apportate da altri; questo senza contare il ruolo fondamentale svolto dagli amministratori a cui viene data la possibilità di accordare diversi privilegi di accesso e scrittura ai file ad utenti differenti.

I CVCS presentano però un limite riscontrabile anche nei sistemi per il controllo locale, un sistema centralizzato è infatti anche un sistema dove tutti i dati risiedono nella medesima posizione, ciò significa che in caso di malfunzionamento (ad esempio un black out) dell'unità centrale tutti i file risulteranno irraggiungibili e nessuno dei collaboratori coinvolti potrà operare su di essi; in tal senso potrebbe rivelarsi ancor peggiore l'eventualità di un danneggiamento con conseguente perdita dei dati.

L'utilizzo di generatori, gruppi di continuità, la manutenzione software e hardware dei terminali server e la creazione periodica di copie di backup non rappresenterebbero in questo senso una garanzia completa di disponibilità del servizio e di integrità dei dati, da qui l'esigenza di sviluppare delle alternative basate sulla decentralizzazione (o distribuzione) del controllo di versione.

## Controllo di versione distribuito

I repository sono definibili come degli archivi per la raccolta ordinata dei dati relativi ad un progetto (ad esempio un package software), tali entità sono fondamentali per il funzionamento dei VCS ma diventano ancora più rilevanti nei DVCS; tali sistemi prevedono infatti che il controllo degli ultimi snapshot generati (una sorta di "istantanee" dei file allo stato corrente) venga affidato ai client che eseguiranno delle copie complete dei repository. Il vantaggio di questo meccanismo risulta evidente rispetto a quello adottato dai sistemi centralizzati o locali, questo perché nel caso di un'interruzione del servizio da parte dei server il repository presente in un client qualunque potrà essere utilizzato per il ripristino.

La dinamica descritta è possibile grazie ad un'apposita funzionalità per la creazione di backup completi denominata checkout dei repository, essa in pratica consente di generare una copia di un repository locale o di un server remoto tramite un comando per la sua clonazione.

A rendere vantaggioso un approccio basato sul controllo di versione distribuito è anche il superamento dell'impostazione "gerarchica" propria dei sistemi centralizzati, un limite a carico del livello di produttività che potrebbe rivelarsi determinante nella gestione del flusso di lavoro; i DVCS come Git permettono infatti di operare su più repository in remoto, in questo modo si avrà la possibilità di lavorare in contemporanea sul medesimo progetto con gruppi di collaboratori differenti seguendo diverse metodologie.

