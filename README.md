# mockation-privacy

Hosts the privacy policy for **Mockation**, the Android location-mocking utility, at
<https://andrew-a-a.github.io/mockation-privacy/> — the URL entered in Play Console under
*Policy → App content → Privacy policy*.

`index.md` is a verbatim copy of `PRIVACY_POLICY.md` in the (private) MOLOCATION repo, which
is the source of truth. To update, copy it over and push:

```bash
cp ../MOLOCATION/PRIVACY_POLICY.md index.md && git commit -am "Sync privacy policy" && git push
```

Nothing else lives here. The app source is not public.
