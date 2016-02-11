# Git-Kochbuch

Kochbuch für typische Situationen mit [Git](https://git-scm.com/).

## Dinge neu machen

### Neues Repo (GitHub -> Lokal)

1. Auf [GitHub](https://github.com/) ein neues Repo **mit** einem README erstellen.
2. Die **HTTPS-Adresse des Repo** in die Zwischenablage kopieren.
3. Auf dem lokalen Rechner mit `cd ~/Documents/foobar/` in das Verzeichnis wechseln, in dem das Repo erstellt werden soll.
4. Mit `git clone https://github.com/user/foo.git` das Repo von GitHub 'runterladen und installieren.
5. Es befindet sich nun im Verzeichns foobar das Verzeichnis foo.

### Neues Repo (Lokal -> GitHub)

1. Im lokalen Ordner mit `git init` ein Repo initialisieren.
2. Mit `git add foo.tex bar.tex` die Dateien anfügen.
3. `git commit -m "erstes Commit"` erstes Commit erzeugen.
4. Auf [GitHub](https://github.com/) ein neues Repo **ohne** einem README erstellen.
5. `git remote add origin https://github.com/mstrehler/vimref.git`
6. `git push -u origin master`

## Branching

### Ein neuer Branch ausgehend von zurückliegendem Commit erzeugen

Man ist fleissig am Codieren und merkt plötzlich, dass man hier eigentlich auf einem neuen Branch sein sollte.
Man will einen neuen Branch erzeugen, ausgehend vom (zurückliegenden) Commit a1b2c3d

```bash
git branch foobar
git reset --hard a1b2c3d
git checkout foobar
```
Alternativ können z.B. 3 Commits zurückgesprungen werden

```bash
git branch foobar
git reset --hard HEAD~3
git checkout foobar
``` 

## Dinge umbenennen

### Branch umbenennen

```bash
git branch -m oldfoo newfoo

```
oder (wenn man schon im umzubenennenden Branch ist)

```bash
git branch -m newfoo
```
 
