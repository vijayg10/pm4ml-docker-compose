# HAProxy SSL Certificate Setup

To generate and use a valid SSL certificate for HAProxy in this directory:

1. **Generate Key and Certificate with Certbot**
   - Use [Certbot](https://certbot.eff.org/) to obtain a certificate for your domain. Example:
     ```sh
     sudo certbot certonly --standalone -d your.domain.com
     ```
   - This will create files like `fullchain.pem` and `privkey.pem` in `/etc/letsencrypt/live/your.domain.com/`.

2. **Construct a Single PEM File**
   - Concatenate the certificate and private key into a single PEM file:
     ```sh
     cat /etc/letsencrypt/live/your.domain.com/fullchain.pem /etc/letsencrypt/live/your.domain.com/privkey.pem > certs/portal.pem
     ```
   - Place the resulting `portal.pem` file in the `certs` folder in this directory.

3. **Restart HAProxy**
   - After updating the certificate, restart HAProxy or your Docker containers to apply the new certificate.

---

**Note:** The `certs/portal.pem` file is required for SSL termination by HAProxy.
