# Lezione 7 - Operazioni sui file

## Ignorare file

È possibile ignorare file e directory in un repository Git utilizzando un file chiamato `.gitignore`. Questo file contiene una lista di file e directory che devono essere ignorati da Git.

Per creare un file `.gitignore`, è possibile creare un nuovo file chiamato `.gitignore` nella directory del repository e aggiungere i file e le directory che si desidera ignorare. Ad esempio, per ignorare tutti i file con estensione `.log`, è possibile aggiungere la seguente riga al file `.gitignore`:

```bash
*.log
```

Una volta creato il file `.gitignore`, è possibile aggiungerlo al repository utilizzando il comando `git add` e eseguire il commit utilizzando il comando `git commit`. Questo permette di ignorare i file e le directory specificati nel file `.gitignore`.

## Rinominare file

Per rinominare un file in un repository Git, è possibile utilizzare il comando `git mv`. Questo comando rinomina un file e aggiunge il nuovo nome al repository.

Ad esempio, per rinominare un file chiamato `file.txt` in `nuovo-file.txt`, è possibile eseguire il seguente comando:

```bash
git mv file.txt nuovo-file.txt
```

Una volta rinominato il file, è possibile aggiungere il nuovo nome al repository utilizzando il comando `git add` e eseguire il commit utilizzando il comando `git commit`.

## Eliminare file

Per eliminare un file da un repository Git, è possibile utilizzare il comando `git rm`. Questo comando rimuove un file dal repository e aggiunge la rimozione al repository.

Ad esempio, per eliminare un file chiamato `file.txt`, è possibile eseguire il seguente comando:

```bash
git rm file.txt
```

Una volta eliminato il file, è possibile aggiungere la rimozione al repository utilizzando il comando `git add` e eseguire il commit utilizzando il comando `git commit`.

## Ripristinare file

È possibile ripristinare un file eliminato o modificato in un repository Git utilizzando il comando `git checkout`. Questo comando ripristina un file alla versione precedente nel repository.

Ad esempio, per ripristinare un file chiamato `file.txt` alla versione precedente, è possibile eseguire il seguente comando:

```bash
git checkout file.txt
```

Una volta ripristinato il file, è possibile aggiungere il ripristino al repository utilizzando il comando `git add` e eseguire il commit utilizzando il comando `git commit`.
