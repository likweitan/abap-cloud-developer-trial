# ABAP Cloud Developer Trial

> [!IMPORTANT]  
> This is a community-maintained backup. This image was originally published by SAP on Docker Hub but has since been removed or moved behind a private registry. This repository serves as a mirror to ensure the image is available for use.

# Disclaimer

This image is not an official SAP product. All intellectual property, trademarks, and software licenses belong to SAP SE. By pulling and using this image, you acknowledge that you are responsible for complying with SAP's original licensing terms and EULA.

# Quick Start

To pull this image from the GitHub Container Registry:

```bash
docker pull ghcr.io/likweitan/abap-cloud-developer-trial:latest
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

1. Logon to your ABAP system with the user `SAP*`, client `000`, same password as for `DEVELOPER` (`DEVELOPER` , client `001`, is locked).
2. Start transaction `SLICENSE`; copy the hardware key.
3. Get the license from `minisap` , choosing the system `A4H`.
4. Back in your ABAP System, start `SLICENSE` again, then choose `Install`.
5. Log off, then log on with the user `DEVELOPER`, client `001`.
The old ("INITIAL") license(s) should be deleted automatically. If not, start `SLICENSE` again; remove the old invalid licenses. (`sap*` is not allowed to delete licenses).

# Default Credentials

The user name is DEVELOPER. The client is either 001 for development or 000 for some admin tasks.

The password is:

- ABAP Cloud Developer Trial 2023, SP00: `ABAPtr2023#00`

This is also predefined (same password) for client 000, client 001: `SAP*`.