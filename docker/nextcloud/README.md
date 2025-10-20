# Manuals
## Setup
1. Deploy Nextcloud using the [compose.yml](https://raw.githubusercontent.com/platnub/mundkur/refs/heads/main/docker/nextcloud/compose.yml?token=GHSAT0AAAAAADNNPT5MLWZ4ZO2E2LS3XYP42HT6TRA) and [.env](https://raw.githubusercontent.com/platnub/mundkur/refs/heads/main/docker/nextcloud/.env?token=GHSAT0AAAAAADNNPT5M4NPELLNSDHPOHYSQ2HT6TZA)
    1. Enable port 8080 in the Docker configuration
    2. Connect to https://IP:8080
    3. Save the passphrase and use it to login
    4. Continue setup and submit subdomain
    5. Optional apps:
        1. ClamAV
        2. Collabora
        3. Imaginary
    6. Download and start containers
    7. Disable port 8080 in the Docker configuration and destroy & deploy the containers
2. Open the terminal of container 'nextcloud-aio-nextcloud'
    1. Run `php occ files:scan-app-data preview -vvv` to scan app-data folder and check data permissions are correct
    2. Run `php occ maintenance:repair --include-expensive`
3. Configre Collabora
    1. Go into administrative settings > office
    2. Append the [Cloudflare IPv4 addresses](https://www.cloudflare.com/en-gb/ips/) to the WOPI allow-list.

## SMTP email setup Google

>[!IMPORTANT]
> Test email may fail because the admin account has an invalid email

1. Create app password for Google account
2. Fill in credentials:
    1. Send mode: 'SMTP'
    2. Encryption: 'SSL'
    3. SMTP address: `smtp.gmail.com:465`
