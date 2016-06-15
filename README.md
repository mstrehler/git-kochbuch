# Git-Kochbuch

Kochbuch für typische Situationen mit [Git](https://git-scm.com/).

## Dinge neu machen

* [Neues Repo von GitHub zum Rechner](neues-repo-github-lokal.md)
* [Neues Repo vom Rechner nach GitHub](neues-repo-lokal-github.md)  

## Branching

### Ein neuer Branch ausgehend von zurückliegendem Commit erzeugen

Man ist fleissig am Codieren und merkt plötzlich, dass man hier eigentlich
Man auf einem neuen Branch sein sollte. will einen neuen Branch erzeugen,
Man ausgehend vom (zurückliegenden) Commit `a1b2c3d`

```bash
git branch foobar
git reset --hard a1b2c3d
git checkout foobar
```

Alternativ kann mit `HEAD~n` n Commits zurückgesprungen werden. So wird hier
3 Commits zurückgesprungen:

```bash
git branch foobar
git reset --hard HEAD~3
git checkout foobar
``` 

## Dinge umbenennen

### Remote Repo umbenennen

Mit `git remote -v` aktueller Name der eingestellten URL für fetch u. push anzeigen.

```bash
git remote set-url origin https://github.com/username/reponame.git
```
Wenn der Username geändert hat, wird man nach `git push` noch nach dem
(neuen) Username sowie dem Passwort gefragt.

### Branch umbenennen

```bash
git branch -m oldfoo newfoo

```
oder (wenn man schon im umzubenennenden Branch ist)

```bash
git branch -m newfoo
```

### Tag umbenennen

First you need to build an alias of the old tag name:

```bash
git tag new_tag_name old_tag_name
```

Then you need to delete the old one locally:

```bash
git tag -d old_tag_name
```

Then delete the tag on you remote location(s):

```bash
# Check your remote sources:
git remote -v

# The argument (3rd) is your remote location,
# the one you can see with `git remote`. In this example: `origin`
git push origin :refs/tags/old_tag_name
```

Finally you need to add your new tag to the remote location. Until you haven't done this, the new tag(s) will not be added:

```bash
git push origin --tags
```

Iterate this for every remote location.

## Dinge löschen

### Remote Branch löschen

```bash
git push origin :bugfix
```
Den seltsamen Syntax kann man sich merken, indem man sich den Befehl `[localbranch]:[remotebranch]` vorstellt --
einfach ohne den lokalen Teil.

## Konflikte bei merge lösen

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
## Diverses

* [Stash](stash.md)
