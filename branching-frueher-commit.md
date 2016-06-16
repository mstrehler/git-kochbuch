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
