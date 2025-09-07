---
layout: default
title: Troubleshooting
parent: Manual Setup (single container)
nav_order: 3
---

# Troubleshooting

This guide covers common issues and troubleshooting steps for AliasVault encountered during installation, updates or general maintenance.

{: .toc }
* TOC
{:toc}

---

## Check Docker Container Status
For any issues you might encounter, the first step is to check the Docker containers health. This will give you a quick insight into the status of the individual containers which will help you identify the root cause of the issue.

1. Check the Docker container running status:
```bash
docker compose ps
```

2. Check the Docker container logs
```
docker compose logs
```

3. Try restarting the Docker container
```bash
docker compose restart
```

---

## Check AliasVault Text Logs
All AliasVault services log information and errors to text files. These files are located in the `logs` directory. You can check the logs of a specific service by running the following command:

```bash
cat logs/[service-name].txt
```

---

## Common Issues
Below are some common issues you might encounter and how to troubleshoot them.

### 1. No emails being received
If you are not receiving emails on your aliases, check the following:
- Verify DNS records are correctly configured
- Ensure ports 25 and 587 are accessible
- Check your server's firewall settings
- Verify that your ISP/hosting provider allows SMTP traffic and does not block port 25

Refer to the [installation guide](./#3-email-server-setup) for more information on how to configure your DNS records and ports.


### 2. Forgot AliasVault Admin Password
If you have lost your admin password, you can reset it by running the install script with the `reset-admin-password` option. This will generate a new random password and update the .env file with it. After that it will restart the AliasVault containers to apply the changes.

1. SSH into the aliasvault container:
```bash
docker compose exec -it aliasvault /bin/bash
```
2. Run the reset-admin-password.sh script:
```bash
./reset-admin-password.sh
```
3. Remember the password outputted by the step above. Then quit out of the SSH session (ctrl+C) and then restart the container:
```bash
docker compose restart
```
4. You can now login to the admin panel (/admin) with the new password.

---

## Other Issues
If you encounter any other issues not mentioned here and need help, please join our Discord server or create an issue on the GitHub repository and we will be happy to help you out.

Find all contact information on the contact page of our website: [https://www.aliasvault.net/contact](https://www.aliasvault.net/contact)