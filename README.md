# apt-repo

## Add GPG key
```
curl -fsSL https://raw.githubusercontent.com/xlionjuan/apt-repo/refs/heads/main/pubkey.gpg | sudo gpg --yes --dearmor --output /usr/share/keyrings/xlion-repo.gpg
```

## Add apt source
### For Ubuntu 24 or Debian 12 (Deb822)

```bash
sudo tee /etc/apt/sources.list.d/xlion-repo.sources << EOF
Types: deb
URIs: https://xlionjuan.github.io/apt-repo
Suites: main
Components: main
Signed-By: /usr/share/keyrings/xlion-repo.gpg
EOF
```

### For older version

```bash
echo "deb [signed-by=/usr/share/keyrings/xlion-repo.gpg] https://xlionjuan.github.io/apt-repo main main" | sudo tee /etc/apt/sources.list.d/xlion-repo.list
```

## Conatins

Latest [RustDesk](https://github.com/rustdesk/rustdesk) Nightly x86_64.
