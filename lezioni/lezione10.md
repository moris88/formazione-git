# Lezione 10 - Tag e Alias

Git presenta alcune funzionalità che permettono di semplificare le operazioni per la ricerca all'interno della cronologia dei progetti registrati nei repository, tagging, e la formulazione rapida delle istruzioni da inviare al DVCS, alias. Il loro utilizzo consente di incrementare la produttività delle sessioni di lavoro, anche nelle fasi di condivisione per lo sviluppo collaborativo.

## Tag

Il comando `git tag` consente di creare un tag per un commit specifico. I tag sono utilizzati per contrassegnare punti specifici nella cronologia dei commit, ad esempio per indicare una versione stabile del software. I tag possono essere annotati o non annotati, e possono essere spostati o eliminati.

### Creazione di un tag

Per creare un tag, è possibile utilizzare il comando `git tag`. Il comando `git tag` consente di creare un tag per il commit corrente. È possibile specificare un messaggio per il tag utilizzando l'opzione `-m`.

Ad esempio, per creare un tag annotato chiamato `v1.0` con il messaggio "Prima versione stabile":

```bash
git tag -a v1.0 -m "Prima versione stabile"
```

Questo comando creerà un tag annotato chiamato `v1.0` per il commit corrente con il messaggio "Prima versione stabile".

### Visualizzazione dei tag

Per visualizzare i tag presenti nel repository, è possibile utilizzare il comando `git tag`. Il comando `git tag` visualizza i tag presenti nel repository.

Ad esempio, per visualizzare i tag presenti nel repository:

```bash
git tag
```

Questo comando visualizzerà i tag presenti nel repository.

### Eliminazione di un tag

Per eliminare un tag, è possibile utilizzare il comando `git tag -d`. Il comando `git tag -d` elimina un tag dal repository.

Ad esempio, per eliminare il tag `v1.0`:

```bash
git tag -d v1.0
```

Questo comando eliminerà il tag `v1.0` dal repository.

## Alias

Gli alias sono comandi personalizzati che consentono di abbreviare i comandi Git più lunghi e complessi. Gli alias possono essere definiti a livello globale o per un repository specifico, e possono essere utilizzati per semplificare le operazioni comuni.

### Creazione di un alias

Per creare un alias, è possibile utilizzare il comando `git config`. Il comando `git config` consente di definire un alias per un comando Git specifico.

Ad esempio, per creare un alias chiamato `co` per il comando `checkout`:

```bash
git config --global alias.co checkout
```

Questo comando creerà un alias chiamato `co` per il comando `checkout`.

### Utilizzo di un alias

Una volta creato un alias, è possibile utilizzarlo come un comando Git normale. Ad esempio, per utilizzare l'alias `co` per eseguire il comando `checkout`:

```bash
git co <branch>
```

Questo comando eseguirà il comando `checkout <branch>` utilizzando l'alias `co`.

### Visualizzazione degli alias

Per visualizzare gli alias definiti nel repository, è possibile utilizzare il comando `git config`. Il comando `git config` consente di visualizzare le configurazioni del repository, compresi gli alias definiti.

Ad esempio, per visualizzare gli alias definiti nel repository:

```bash
git config --get-regexp alias
```

Questo comando visualizzerà gli alias definiti nel repository.

### Eliminazione di un alias

Per eliminare un alias definito nel repository, è possibile utilizzare il comando `git config --unset`. Il comando `git config --unset` consente di eliminare una configurazione specifica dal repository.

Ad esempio, per eliminare l'alias `co` definito nel repository:

```bash
git config --unset alias.co
```

Questo comando eliminerà l'alias `co` definito nel repository.

### Alias ADOG

Un esempio di alias utile è l'alias `adog`, che visualizza la cronologia dei commit in un formato più leggibile. Per creare l'alias `adog`:

```bash
git config --global alias.adog "log --all --decorate --oneline --graph"
```

Una volta creato l'alias `adog`, è possibile utilizzarlo per visualizzare la cronologia dei commit in un formato più leggibile:

```bash
git adog
```

Questo comando visualizzerà la cronologia dei commit in un formato più leggibile.
