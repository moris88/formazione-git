# Lezione 3 - Installazione e Configurazione di Git

## Installazione di Git

Il primo passo per iniziare a utilizzare Git è installare il software sul proprio computer. Git è un software open source e può essere installato su Windows, Linux e macOS.

### Windows

Per installare Git su Windows, è possibile scaricare il pacchetto di installazione dal sito ufficiale [https://git-scm.com/](https://git-scm.com/).

### Linux

Per installare Git su Linux, è possibile utilizzare il package manager del proprio sistema operativo. Ad esempio, su Ubuntu è possibile installare Git con il seguente comando:

```bash
sudo apt-get install git
```

### macOS

Per installare Git su macOS, è possibile utilizzare il package manager Homebrew. Per installare Homebrew, è possibile utilizzare il seguente comando:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Una volta installato Homebrew, è possibile installare Git con il seguente comando:

```bash
brew install git
```

## Configurazione di Git

Dopo aver installato Git, è necessario configurare il proprio nome utente e indirizzo email. Queste informazioni verranno utilizzate per identificare le modifiche apportate ai file.

Per configurare il nome utente, è possibile utilizzare il seguente comando:

```bash
git config --global user.name "Nome Cognome"
```

Per configurare l'indirizzo email, è possibile utilizzare il seguente comando:

```bash
git config --global user.email "Email"
```

## Verifica dell'installazione e configurazione

Per verificare che Git sia stato installato correttamente e che la configurazione sia stata impostata correttamente, è possibile utilizzare i seguenti comandi:

```bash
git --version
git config --list
```

Il primo comando restituirà la versione di Git installata sul sistema, mentre il secondo comando restituirà la lista delle configurazioni impostate per l'utente.
