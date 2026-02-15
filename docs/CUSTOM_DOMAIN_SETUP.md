# Custom Domain Setup for GitHub Pages

This repository is configured to use a custom domain: **fimdim.com**

## Current Status

The CNAME file has been added to the repository to specify the custom domain. However, additional steps are required to fully enable HTTPS.

## DNS Configuration Required

To complete the setup and enable HTTPS for your GitHub Pages site, you need to configure your DNS settings with your domain registrar:

### Option 1: Using A Records (Recommended for Apex Domain)

Add the following A records for `fimdim.com`:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

### Option 2: Using CNAME Record (For Subdomain)

If using a subdomain like `www.fimdim.com`, add a CNAME record:

```
www.fimdim.com CNAME fimdim.github.io
```

## Enabling HTTPS

After DNS configuration:

1. **Wait for DNS propagation** (can take up to 24-48 hours)
2. **GitHub will automatically verify your domain** and issue an SSL certificate
3. **Navigate to Repository Settings → Pages**
4. **Check the "Enforce HTTPS" option** once the certificate is issued

## Verification

You can verify DNS configuration using:

```bash
# Check A records
dig fimdim.com +short

# Check CNAME record (if using subdomain)
dig www.fimdim.com +short
```

## Troubleshooting

If "Enforce HTTPS" is unavailable:

- Ensure DNS records are properly configured
- Wait for GitHub to issue the SSL certificate (can take up to 24 hours after DNS is configured)
- Check for any DNS propagation issues
- Verify the CNAME file in the repository contains the correct domain

## References

- [Managing a custom domain for your GitHub Pages site](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)
- [Securing your GitHub Pages site with HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
- [Troubleshooting custom domains and GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages)
