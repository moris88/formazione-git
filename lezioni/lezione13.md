# Lezione 13 - Info e fusione di branch

In questa lezione vedremo come ottenere informazioni sui branch presenti nel repository e come effettuare la fusione di branch.

## Visualizzazione dei branch

Per visualizzare i branch presenti nel repository, è possibile utilizzare il comando `git branch`. Il comando `git branch` visualizza i branch presenti nel repository, in particolare visualizza il branch corrente e i branch disponibili.

Ad esempio, per visualizzare i branch presenti nel repository:

```bash
git branch
```

Questo comando visualizzerà i branch presenti nel repository.

N.B.: Facendo attenzione al modo in cui viene presentato l'output di git branch è possibile notare che il nome del ramo master è preceduto da un asterisco ("*"), questo simbolo viene utilizzato da Git per indicare all'utilizzatore il ramo corrente, cioè quello in cui egli si trova attualmente e verso il quale è rivolto il puntatore dei rami. L'asterisco funziona in sostanza come indicatore per capire in quale posizione ci troviamo rispetto al nostro piano di lavoro.

## Stato delle fusioni

Un altro utilizzo di git branch riguarda la possibilità di visualizzare i rami che sono stati sottoposti a merging e quelli che invece non hanno subito una fusione.

L'istruzione git branch seguita dal parametro --merged per operare una verifica dei rami che hanno subito una fusione e non sono stati cancellati; l'opzione --no-merged consente al contrario di visualizzare i rami esistenti che non sono stati sottoposti a merging.

Ad esempio, per visualizzare i branch che sono stati sottoposti a merging:

```bash
git branch --merged
```

Questo comando visualizzerà i branch che sono stati sottoposti a merging.

Per visualizzare i branch che non sono stati sottoposti a merging:

```bash
git branch --no-merged
```

Questo comando visualizzerà i branch che non sono stati sottoposti a merging.

## Sicurezza dei rami

Per evitare la perdita di dati è possibile utilizzare il comando `git branch` seguito dal parametro -d per eliminare un ramo che è stato sottoposto a merging. Questo comando eliminerà il ramo specificato.

Ad esempio, per eliminare il branch `feature`:

```bash
git branch -d feature
```

Questo comando eliminerà il branch `feature`.

## Visualizzare i commit dei rami

Il comando `git branch` può essere associato all'argomento -v per ottenere informazioni riguardo agli ultimi commit effettuati.

Ad esempio, per visualizzare i commit associati ai branch presenti nel repository:

```bash
git branch -v
```

Questo comando visualizzerà i commit associati ai branch presenti nel repository.

Il report prodotto è di facile lettura. I rami vengono disposti sulla base della cronologia dei commit a partire da quello eseguito più di recente.
