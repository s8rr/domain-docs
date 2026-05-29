---
order: 2000
label: GitHub Pages
icon: mark-github
tags: guides
---

## Setting up GitHub pages with an code-space.me subdomain

This guide will walk you through the process of setting up a GitHub Pages site and pointing your code-space.me subdomain to it.

### Creating a GitHub Pages repository

First, you'll need to create a site on GitHub Pages. Follow the instructions in the [GitHub Pages Getting Started Guide](https://docs.github.com/en/pages/getting-started-with-github-pages).

### Creating the domain file

Create a JSON file inside `domains` directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "records": {
        "CNAME": "github-username.github.io"
    }
}
```

### Configuring

- After the pull request is merged, you may see a **404** error on `subdomain.code-space.me` or the wrong site. To fix this issue, go to your GitHub pages repository and navigate to: **Settings > GitHub pages > Custom Domain** and add `subdomain.code-space.me` in the given field. *Only do this **after** your pull request is merged.*
- Check the **Enforce HTTPS** checkbox below the custom domain input.
- Wait some time and your site should be live!

## Verifying your code-space.me Subdomain with GitHub Pages

### Get your verification string

1. Navigate to GitHub, press your profile icon at the top right, and press `Settings`.

![](../media/github_pages_verification/step_1.png)

2. Press `Pages`.

![](../media/github_pages_verification/step_2.png)

3. Press `Add a domain`.

![](../media/github_pages_verification/step_3.png)

4. In the field that appears, type your code-space.me subdomain name (e.g. `myname.code-space.me`) and press `Add domain`.

![](../media/github_pages_verification/step_4.png)

5. Copy the hostname and the verification string.

![](../media/github_pages_verification/step_5.png)

### Create the domain file

Create a JSON file inside the `domains/` directory called `domains/hostname.subdomain.json` using the hostname you copied in step 5 and subdomain (`subdomain.code-space.me`) with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "github-username",
        "email": "your-email@gmail.com"
    },
    "records": {
        "TXT": "github-verification-string"
    }
}
```

### Configuration

After your pull request has been merged, repeat the steps to get the verification string and press the `Verify` button.
If it shows an error such as `Unable to verify your domain`, try waiting a few minutes (sometimes up to 24 hours) as the DNS records may not have propagated yet.
