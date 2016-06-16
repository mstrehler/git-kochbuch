### Merge-Konflikt bei PDF-Datei (binary) lösen

Binary aus aktuellem Branch verwenden (allenfalls, wenn aus dem gemergten TeX-File bereits eine neue PDF-Datei erzeugt wurde):
Um den Konflikt zu lösen und das Binary aus **diesem Branch** (hier: `somefile.pdf`) zu behalten:

```bash
git add somefile.pdf 
git commit –m “My commit message for the merge”
```

Wenn man das Binary (hier: `somefile.pdf`) aus dem **anderen Branch** haben möchte, muss zuerst dieses herangeschafft werden:

```bash
git checkout otherbranch somefile.pdf
```

Jetzt hat man die gewünschte Version im Arbeitsverzeichnis und es kann angefügt und committed werden.

```bash
git add somefile.pdf
git commit –m “My commit message for the merge”
```
