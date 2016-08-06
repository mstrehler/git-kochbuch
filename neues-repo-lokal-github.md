# Neues Repo vom eigenen Rechner nach GitHub

## Ausgangslage

Auf den lokalen Rechner befindet sich ein Repo, dass man nach GitHub "klonen" will.
Klonen steht hier in Anführungszeichen, weil es hier nicht ganz der richtige Ausdruck ist.
Sondern man erzeugt auf GitHub ein neues Repo, das mit dem lokalen Repo gemergt wird.
Man hat also am Schluss zwei commits mehr: nämlich das "Initial commit" von GitHub
und das Merge-Commit.

## Schritt für Schritt

1. Auf [GitHub](https://github.com/) ein neues Repo **ohne** einem README erstellen.
2. Die URL unter dem Button "Clone or download" ins Clipboard kopieren.
3. Im lokalen Repo die Adresse abspeichern: `git remote add origin https://github.com/mstrehler/name.git`
4. Mit `git pull origin master` die (neuen) Dateien von GitHub hinunterladen und in das lokale Repo mergen.
5. Es öffnet sich ein Editorfenster, in dem die Commit-Meldung des Merges editiert werden kann. Hier einfach speichern.
6. Mit `git push -u origin master` nun das lokale Repo hochladen. Dabei ist `-u` das Kürzel für `--set-upstream`.
