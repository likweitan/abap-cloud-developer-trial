# ABAP Cloud Developer Trial - Docker

<p align="center">
    <picture>
        <source media="(prefers-color-scheme: light)" srcset="https://github.com/user-attachments/assets/8e47601e-b754-46c5-9544-04ae2f21ca3e">
        <img src="https://github.com/user-attachments/assets/8e47601e-b754-46c5-9544-04ae2f21ca3e" alt="ABAP Cloud Developer Trial" width="200">
    </picture>
</p>

> [!CAUTION]
> **This repository has been archived as of 17 May 2026.**
>
> SAP has contacted me regarding this repository. The ABAP Cloud Developer Trial 2023 image was licensed for **personal use only** — not for distribution or redistribution. Hosting it here violates the license agreement I accepted when downloading it.
>
> The container image at `ghcr.io/likweitan/abap-cloud-developer-trial:2023` has been unpublished. This repository is now **read-only and archived** for historical reference. Please do not attempt to re-mirror or redistribute this image.
>
> See the [official SAP announcement](https://community.sap.com/t5/technology-blog-posts-by-sap/abap-cloud-developer-trial-2023-available-now/ba-p/14057183) for background. SAP has confirmed the trial has been discontinued and cannot be offered again officially at this time.

---

> [!IMPORTANT]
> ~~This is a community-maintained backup. This image was originally published by SAP on Docker Hub but has since been removed or moved behind a private registry. This repository serves as a mirror to ensure the image is available for use.~~
>
> *This section is retained for historical context only. The image is no longer available.*

# Disclaimer

This image is not an official SAP product. All intellectual property, trademarks, and software licenses belong to SAP SE. By pulling and using this image, you acknowledge that you are responsible for complying with SAP's original licensing terms and EULA.

# Quick Start

> [!WARNING]
> The image below has been unpublished. The commands below are preserved for reference only and will no longer work after 17 May 2026.

To pull this image from the GitHub Container Registry:

```bash
docker pull ghcr.io/likweitan/abap-cloud-developer-trial:2023
```

To run the container:

**GNU/Linux**
```bash
docker run --stop-timeout 3600 -it --name a4h -h vhcala4hci ghcr.io/likweitan/abap-cloud-developer-trial:2023 -agree-to-sap-license
```

**Others**
```bash
docker run --stop-timeout 3600 -i --name a4h -h vhcala4hci -p 3200:3200 -p 3300:3300 -p 8443:8443 -p 30213:30213 -p 50000:50000 -p 50001:50001 ghcr.io/likweitan/abap-cloud-developer-trial:2023 -skip-limits-check -agree-to-sap-license
```

# ABAP License

The ABAP license supplied with the Docker image lasts only three months. Therefore, you should download and import the demo license as follows:

1. Logon to your ABAP system with the user `SAP*`, client `000`, same password as for `DEVELOPER` (`DEVELOPER`, client `001`, is locked).
2. Start transaction `SLICENSE`; copy the hardware key.
3. Get the license from [minisap](https://go.support.sap.com/minisap/#/minisap), choosing the system `A4H`.
4. Back in your ABAP System, start `SLICENSE` again, then choose `Install`.
5. Log off, then log on with the user `DEVELOPER`, client `001`.

The old ("INITIAL") license(s) should be deleted automatically. If not, start `SLICENSE` again; remove the old invalid licenses. (`sap*` is not allowed to delete licenses).

# Default Credentials

The user name is `DEVELOPER`. The client is either `001` for development or `000` for some admin tasks.

The password is:

- ABAP Cloud Developer Trial 2023, SP00: `ABAPtr2023#00`

This is also predefined (same password) for client `000`, client `001`: `SAP*`.
