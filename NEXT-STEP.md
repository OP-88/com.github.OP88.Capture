# Manual step needed: Update git source in manifest

In `com.github.OP88.Capture.yml`, find the **capture module** near the end of the file (around line 90+):

```yaml
- name: capture
  buildsystem: simple
  build-commands:
    # ... lots of commands ...
  sources:
    - type: dir
      path: .
```

**Replace the sources section** with:
```yaml
  sources:
    - type: git
      url: https://github.com/OP-88/Capture.git
      tag: v1.0.4
      commit: fe20cb6f048f209707ca32d14df20d207966040e
```

Save the file, then run:
```bash
cd ~/Verba-mvp/com.github.OP88.Capture
git add .
git commit -m "Initial Flathub submission for Capture v1.0.4"
git push origin main
```
