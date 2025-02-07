Initialize after init repo roms

```
git clone https://github.com/Soverzion-Peridot/local_manifest.git -b vic-hals .repo/local_manifests/
```

And sync repo
```
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)
```

Patch this to add UDFPS support in perindo
```
cd frameworks/base
curl -s https://raw.githubusercontent.com/Soverzion-Peridot/patches/refs/heads/main/0001-biometrics-virtualhal-Revert-for-mfp-daemon-to-work.patch -s | git am
```
