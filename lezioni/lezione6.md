# Lezione 6 - Gestione dello staging

La gestione dello staging è probabilmente una delle fasi più articolate per quanto riguarda le procedure di versioning con Git, l'area di stage rappresenta infatti una sorta di entità intermedia tra la directory di lavoro e la directory del DVCS; una volta eseguite le operazioni relative allo staging, sarà possibile effettuare il commit delle modifiche apportate al proprio progetto, tenendo a mente però che qualsiasi elemento unstaged, cioè qualunque file che sia stato creato o modificato senza essere stato passato come argomento a `git add`, non potrà essere committato.

## Staging e tracciamento

La modifica dei file già tracciati rappresenta un intervento abbastanza frequente nel controllo di versione, a questo proposito rimangono però da chiarire le implicazioni di tale processo sullo staging.
L'elemento di novità è rappresentato dalla notifica "Changed but not staged for commit", sostanzialmente ci si trova a dover gestire un file in piena fase di tracciamento che ha subito una modifica nella directory di lavoro ma non è stato ancora sottoposto a staging; l'ingresso in area di stage sarà possibile anche in questo caso tramite l'utilizzo dell'istruzione git add che, come risulta ormai chiaro, non viene chiamato in causa soltanto per il tracciamento e lo staging di file addizionali e permette di lavorare anche su risorse preesistenti adottando la medesima sintassi.

Una volta passato il nome del file come argomento al comando per lo staging si potrà effettuare un'ulteriore verifica sullo stato del progetto che dovrebbe confermare l'assenza di file al di fuori dell'area di stage:

```bash
git add .
git status
```

## git diff come alternativa a git status

Uno dei grandi limiti di git status sta nel fatto che esso permette di identificare i file che hanno subito delle modifiche ma non consente di capire quali cambiamenti siano stati apportati ad esso; per colmare tale lacuna si è scelto di fornire un comando in grado di produrre output nettamente più particolareggiati: `git diff`.

```bash
git diff "nome file"
```

Il risultato della chiamata all'istruzione mostra rispettivamente in rosso e in verde la precedente modifica ormai già in stage e quella appena effettuata senza il successivo staging tramite git add; nel caso in cui non dovessero essere presenti modifiche da registrare in area di stage git diff non produrrà alcun output.

Sempre a proposito di questo comando, l'utilizzatore dovrà ricordare che git diff non si occupa di mostrare tutte le modifiche eseguite a partire dall'ultimo commit effettuato, esso infatti permetterà di visualizzare i soli cambiamenti non ancora in stage quando presenti.

## Evitare il transito nell'area di stage

Per quanto importantissima ai fini della revisione in fase di implementazione di un progetto, l'area di stage potrà essere bypassata evitando quindi che un file modificato transiti attraverso di essa. Tale risorsa verrà trasferita dalla working directory a quella di Git associando alla già citata istruzione git commit -m l'argomento -a:

```bash
git commit -a -m "Messaggio del commit"
```

Anche nel caso in cui un file dovesse aver subito delle modifiche senza una successiva chiamata a git add, l'opzione -a garantirà che una successiva esecuzione di git status o git diff non segnalino la presenza di cambiamenti non registrati in area di stage.
