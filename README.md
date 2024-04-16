[![Update packages](https://github.com/radxa-repo/sid-test/actions/workflows/update.yaml/badge.svg)](https://github.com/radxa-repo/sid-test/actions/workflows/update.yaml)

# sid-test

## Usage

```bash
temp=$(mktemp)
curl -L --output "$temp" "https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/radxa-archive-keyring_$(curl -L https://github.com/radxa-pkg/radxa-archive-keyring/releases/latest/download/VERSION)_all.deb"
sudo dpkg -i "$temp"
rm -f "$temp"
source /etc/os-release
sudo tee /etc/apt/sources.list.d/radxa.list <<< "deb [signed-by=/usr/share/keyrings/radxa-archive-keyring.gpg] https://radxa-repo.github.io/sid-test/ $VERSION_CODENAME main"
sudo apt update
```
