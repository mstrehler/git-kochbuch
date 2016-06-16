## Stashing (Zwischenspeichern eines unfertigen Commits)

stash: englisch für Geheimversteck, Lager.

Um eine angefangene Arbeit, die noch nicht commit-würdig ist, zu speichern dient folgender Befehl:

```bash
git stash
```
So kann dann auch ohne Commit in einen anderen Branch gewechselt werden.

Gibt eine Liste mit den gespeicherten Stashs aus:

```bash
git stash list
```

(Wieder-)einsetzen (to apply) des letzen Stash, resp. mit Wiederherstellen des Stage-Zustandes (--index),
resp. Wiederherstellen eines bestimmten Stash

```bash
git stash apply
git stash apply --index
git stash apply stash@{2}
```
