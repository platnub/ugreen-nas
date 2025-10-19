# Manuals
## Setup
1. Deploy Nextcloud using the [compose.yml](https://raw.githubusercontent.com/platnub/mundkur/refs/heads/main/docker/nextcloud/compose.yml?token=GHSAT0AAAAAADNNPT5MLWZ4ZO2E2LS3XYP42HT6TRA) and [.env](https://raw.githubusercontent.com/platnub/mundkur/refs/heads/main/docker/nextcloud/.env?token=GHSAT0AAAAAADNNPT5M4NPELLNSDHPOHYSQ2HT6TZA) and connect to https://IP:8080
    1. Save the Passphrase
    2. Continue setup and submit subdomain
    3. Optional apps:
        1. ClamAV
        2. Collabora
        3. Imaginary
    4. Download and start containers
2. Connect to the Ugreen NAS using SSH
    1. Run `docker exec --user www-data -it nextcloud-aio-nextcloud php occ files:scan-app-data preview -vvv` to scan app-data folder and check data permissions are correct

## SMTP email setup Google

>[!IMPORTANT]
> Test email may fail because the admin account has an invalid email

1. Create app password
2. Fill in credentials:
    1. Send mode: 'SMTP'
    2. Encryption: 'SSL'
    3. SMTP address: `smtp.gmail.com:465`
