# Manuals
## Ugreen Setup
1. Initial seup
  1. Admin account
2. Enable SSH
3. Create shared folders
  1. 'komodo'
  2. 'cloudflared'
  3. 'nextcloud'
5. Install apps
  1. Docker
3. Setup Komodo
  1. Connect through SSH
  2. Go to `cd /volume1/komodo`
  3. Using instructions from [the Komodo setup guide](https://komo.do/docs/setup/mongo), install Komodo
    1. ```
       wget -P komodo https://raw.githubusercontent.com/moghtech/komodo/main/compose/mongo.compose.yaml && \
        wget -P komodo https://raw.githubusercontent.com/moghtech/komodo/main/compose/compose.env && mv komodo docker
       ```
    2. Generate
