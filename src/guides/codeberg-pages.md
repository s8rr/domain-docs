---
order: 1700
label: Codeberg Pages
icon: /media/codeberg.svg
tags: guides
---

# Setting up Codeberg Pages with an code-space.me subdomain

This guide will walk you through the process of setting up a Codeberg Pages website and pointing your code-space.me subdomain to it.

## Create a Codeberg Pages Website

First, you'll need to create a website on Codeberg Pages. Follow the instructions in the [Codeberg Pages Guide](https://docs.codeberg.org/codeberg-pages/).

### Create the Domain File

Create a JSON file inside domains directory (`domains/subdomain.json`) with the following content and submit a pull request:

```json
{
    "owner": {
        "username": "your-codeberg-username",
        "email": "your-email@example.com"
    },
    "records": {
        "CNAME": "pages.your-codeberg-username.codeberg.page"
    }
}
```

### Add `.domains` file

Once your PR is merged, Make a `.domains` file to point your website to your new `.code-space.me` domain and add your subdomain (`your-subdomain.code-space.me`) to it.

### Done!

If you've followed everything correctly your website should be live :)
