### Remote Repo umbenennen

Mit `git remote -v` aktueller Name der eingestellten URL für fetch u. push anzeigen.

```bash
git remote set-url origin https://github.com/username/reponame.git
```
Wenn der Username geändert hat, wird man nach `git push` noch nach dem
(neuen) Username sowie dem Passwort gefragt.
