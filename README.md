# allthenticate-arch

1. Download from here: https://debian.allthenticate.com/stable/ubuntu/pool/noble/main/allthenticate-service_2.2.16_amd64.deb
2. Use X11 for the client to pair
3. Run Service Like this
```bash
sudo /usr/bin/env SSL_CERT_DIR=/etc/ssl/certs/ /opt/sda/bin/sda-service
```
4. Run `chmod +x libsda_desktop_pam.so`
5. Add the following in `/etc/pam.d/sudo` for sudo passwordless
```
auth sufficient libsda_desktop_pam.so
```
