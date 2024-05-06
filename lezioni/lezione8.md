# Lezione 8 - Annullamento e cronologia delle modifiche

Git non va considerato tanto uno strumento per lo sviluppo quanto una soluzione per la gestione delle fasi di sviluppo, ecco perché poter gestire le operazioni effettuate durante il versioning (ed eventualmente annullarle) registrando i diversi passaggi cronologicamente, può rivelarsi fondamentale per l'economia di un progetto. Alcuni dei comandi descritti in questa parte della guida, in particolare per quanto riguarda l'annullamento, non sono reversibili, motivo per il quale si consiglia di utilizzarli con la dovuta attenzione.

## Annullamento delle modifiche

Il comando `git commit` offre un'opzione, `--amend`, che consente di risolvere una problematica abbastanza frequente per chi utilizza strumenti destinati al controllo di versione, accade infatti abbastanza spesso che un commit venga effettuato prematuramente, dimenticando per esempio di includere un file invece coinvolto nell'aggiornamento del progetto corrente; nello stesso modo l'utilizzatore potrebbe aver lanciato l'ultimo commit associando ad esso un messaggio errato.

Analizzando le operazioni effettuate si nota innanzitutto che, esattamente come nel caso dei commit per l'aggiornamento del repository presente nella directory del DVCS, anche quando si utilizza l'opzione `--amend` non si avrà la necessità di passare il nome del file o dei file coinvolti come parametri per l'istruzione; un commit riguarda infatti tutte le modifiche effettuate a carico di un progetto a partire dall'istantanea precedente, così sarà anche per il suo annullamento.

Quest'ultima osservazione risulta utile per capire come il compito di `--amend` sia quello di adottare le informazioni allocate in stage per l'esecuzione del commit, infatti, nel caso in cui non siano state apportate delle modifiche a partire dall'ultimo commit prima del comando per l'annullamento, l'istantanea generata sarà la medesima con l'eccezione della descrizione associata al commit.

Si noti infine che il lancio di `git commit` con opzione `--amend` determinerà automaticamente l'apertura dell'editor predefinito associato alla propria installazione del DVCS, cosa che permetterà di effettuare l'intervento di correzione tralasciato prima dell'ultimo commit.

## Annullamento dei commit e staging

Il comando `git reset` consente di annullare i commit effettuati, in particolare si possono annullare i commit effettuati in locale, ma non ancora inviati al repository remoto. Il comando `git reset` può essere utilizzato con tre opzioni differenti:  

- `--soft`: annulla il commit, ma mantiene le modifiche effettuate in stage, permettendo all'utilizzatore di apportare delle modifiche e di effettuare un nuovo commit.
- `--mixed`: annulla il commit e le modifiche effettuate in stage, ma mantiene le modifiche effettuate nei file.
- `--hard`: annulla il commit e le modifiche effettuate in stage, eliminando le modifiche effettuate nei file.

Per annullare il commit e mantenere le modifiche effettuate in stage, si può utilizzare il comando `git reset --soft HEAD^`. Per annullare il commit e le modifiche effettuate in stage, ma mantenere le modifiche effettuate nei file, si può utilizzare il comando `git reset --mixed HEAD^`. Per annullare il commit e le modifiche effettuate in stage, eliminando le modifiche effettuate nei file, si può utilizzare il comando `git reset --hard HEAD^`.

## Cronologia dei commit

Il comando `git log` consente di visualizzare la cronologia delle modifiche effettuate. Il comando `git log` visualizza le informazioni relative ai commit effettuati, in particolare visualizza il codice SHA del commit, l'autore del commit, la data e l'ora del commit e il messaggio associato al commit. Il comando `git log` può essere utilizzato con diverse opzioni, ad esempio si può utilizzare l'opzione `--oneline` per visualizzare le informazioni relative ai commit in una sola riga, oppure si può utilizzare l'opzione `--graph` per visualizzare le informazioni relative ai commit in forma grafica.

## Revert di un commit

Il comando `git revert` consente di annullare un commit effettuato, creando un nuovo commit che annulla le modifiche effettuate nel commit precedente. Il comando `git revert` può essere utilizzato con l'opzione `-n` per annullare un commit senza creare un nuovo commit.
