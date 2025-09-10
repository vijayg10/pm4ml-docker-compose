# HAProxy SSL Certificate Setup

To generate and use a valid SSL certificate for HAProxy using the automated Docker setup:

## Automated Certificate Generation

1. **Stop HAProxy Container**
   ```sh
   docker-compose --profile gateway stop haproxy
   ```

2. **Run Certificate Generation**
   ```sh
   docker-compose -f docker-compose-certbot.yaml up
   ```
   This will:
   - Run Certbot in standalone mode to obtain certificates for `portal.${PM4ML_DOMAIN}`
   - Automatically combine `fullchain.pem` and `privkey.pem` into `certs/portal.pem`
   - Place the combined certificate file in the correct location for HAProxy

3. **Restart HAProxy**
   ```sh
   docker-compose --profile gateway up -d haproxy
   ```

---

**Note:** The `certs/portal.pem` file is required for SSL termination by HAProxy and must contain both the certificate chain and private key.
