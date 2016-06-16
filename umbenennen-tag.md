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
