# Manuals
## Ugreen Setup
1. Initial seup
    1. Admin account
2. Enable SSH
3. Create shared folders
    1. 'komodo'
    2. 'cloudflared'
    3. 'nextcloud'
4. Install apps
    1. Docker
5. Setup Komodo
    1. Connect through SSH
    2. Go to `cd /volume1/komodo`
    3. Using instructions from [the Komodo setup guide](https://komo.do/docs/setup/mongo), install Komodo
        1. ```
           wget -P komodo https://raw.githubusercontent.com/moghtech/komodo/main/compose/mongo.compose.yaml && wget -P komodo https://raw.githubusercontent.com/moghtech/komodo/main/compose/compose.env && mv komodo docker
           ```
        2. Generate 2x random values for PASSKEY and JWT using `openssl rand -hex 64`
        3. Modify TZ to 'Europe/Amsterdam'
        4. Create an admin password 'KOMODO_INIT_ADMIN_PASSWORD'
        5. Fill in Priperhy passkey as the value generated before
        6. Launch Komodo using
           ```
           cd /volume1/komodo && docker compose -p komodo -f docker/mongo.compose.yaml --env-file docker/compose.env up -d
           ```
6. Deploy a Cloudflared container using the TUNNEL_TOKEN
7. Deploy Nextcloud and connect to https://IP:8080
    1. Save the Passphrase
    2. Continue setup and submit subdomain
    3. Optional apps:
        1. ClamAV
        2. Collabora
        3. Imaginary
    4. Download and start containers
