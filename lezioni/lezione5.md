# Lezione 5 - Stato dei file

Git non è propriamente uno strumento "di" sviluppo ma un tool "per" lo sviluppo, la sua funzione più importante è quindi probabilmente quella di permettere il tracciamento dei file contenuti all'interno dei repository, tale attività consente di avere una rappresentazione chiara dello stato (o status) del contenuto di un progetto e per essa sono disponibili alcune istruzioni che permetteranno di verificare il risultato degli interventi apportati nel corso delle sessioni di lavoro. Le istantanee stesse, o snapshots, costituiscono delle certificazioni riguardanti le modifiche di stato.

## Stato dei file

Il comando `git status` permette di visualizzare lo stato dei file all'interno di un repository Git. Questo comando mostra quali file sono stati modificati, quali file sono stati aggiunti all'area di stage e quali file sono pronti per il commit.

Per visualizzare lo stato dei file all'interno di un repository, è possibile utilizzare il comando `git status`. Ad esempio, per visualizzare lo stato dei file all'interno del repository corrente, è possibile eseguire il seguente comando:

```bash
git status
```

Questo comando restituirà un elenco dei file che sono stati modificati, aggiunti all'area di stage o pronti per il commit. Inoltre, il comando `git status` mostrerà anche informazioni aggiuntive, come il branch corrente e eventuali conflitti di merge.

## Tracciamento dei file aggiuntivi

Il semplice fatto di aver aggiunto un file nel proprio progetto non ne determinata automaticamente il tracciamento. Per formulare un esempio a conferma di quanto affermato, sempre dall'interno della directory di lavoro basterà utilizzare il comando vim per la creazione di un file privo di estensione denominato NOTES; una volta scritto un semplice contenuto nel file (ad esempio "Author's Notes"), sarà possibile salvare le modifiche effettuate e uscire dal file tramite il tasto [ESC] seguito da [ZZ] (in maiuscolo come riportato). Fatto questo, si dovrà lanciare nuovamente l'istruzione `git status`.

L'output prodotto da Git in seguito all'ennesima verifica di stato proposta indica chiaramente che il DVCS è in grado di rilevare la presenza del nuovo file, ciò perché quest'ultimo non era compreso nell'istantanea relativa al commit operato in precedenza, esso però risulterà untracked e quindi non tracciato; la responsabilità del tracciamento di file addizionali ricade interamente sullo sviluppatore, sarà infatti quest'ultimo a decidere se essi dovranno essere tracciati e quindi inclusi negli snapshots dei propri commit, in questo modo il sistema impedirà l'inclusione involontaria di componenti di progetto non necessarie, potenzialmente dannose o indesiderate.

L'attività di tracciamento di un file dovrà essere quindi inizializzata e, per far questo, si ricorrerà all'istruzione `git add` seguita dal nome del file da tracciare passato come parametro. Nel caso specifico dell'esempio proposto si dovrà quindi digitare:

```bash
git add NOTES
```

A questo punto anche il nuovo file verrà coinvolto nel tracciamento del sistema, a conferma di ciò sarà sufficiente lanciare un ulteriore comando per la verifica di stato del progetto.

E' bene tenere presente, è l'output mostrato in figura lo testimonia tramite la notifica "Changes to be committed", che il nuovo stato del file aggiunto riguarda l'area di stage, motivo per il quale esso rientrerà in un'istantanea rispettando la cronologia degli snapshots soltanto in seguito al commit successivo.

Lanciando ancora una volta il comando `git status`, il DVCS confermerà la rilevazione dell'ultimo commit effettuato tramite la notifica "Your branch is ahead of 'origin/master' by 1 commit", contestualmente verrà certificata l'assenza di ulteriori modifiche successive al commit (nothing to commit, working directory clean) e di file non tracciati.

## La logica del tracciamento

Come anticipato ampiamente nel corso di questo capitolo, l'attività di tracciamento è fondamentale in Git in quanto influenza la composizione delle varie istantanee prodotte nel corso della lavorazione di un progetto; per Git un nuovo file nasce (o meglio, "si presenta") come non tracciato è questo è il suo stato iniziale, nel momento stesso in cui tale file viene aggiunto esso è immodificato perché uguale all'originale che l'utilizzatore ha deciso di includere. Un caso particolare è quello della clonazione, in seguito alla quale tutti i file prelevati dal repository scelto vengono classificati da subito come tracciati e non modificati.

Una volta editato un file esso sarà invece considerato come modificato e si potrà procedere con il suo inserimento in area di stage. Dopo lo staging e in seguito ad un commit, il file ritornerà ad essere immodificato e, nel caso in cui si voglia concluderne il tracciamento, esso dovrà essere rimosso.

La logica del tracciamento del DVCS prevede che ciascun file appartenente ad una working directory di lavoro corrisponda a due stati specifici e concettualmente opposti, cioè tracciato o non tracciato. Un file tracciato si caratterizza per il fatto di essere già parte integrante dell'ultima istantanea registrata, questo indipendentemente dal fatto che abbia subito o meno delle modifiche; appartengono invece alla seconda categoria tutti i file non sottoposti a tracciamento, essi possono essere presenti nella directory di lavoro ma non nell'area di stage o nell'istantanea del progetto.
