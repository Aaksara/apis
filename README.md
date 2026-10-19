# AKSARA API

[Bruno](https://www.usebruno.com/) collection for the
[AKSARA backend](https://github.com/Aaksara/backend): every endpoint with an example
request, its rules and its responses.

## Use it

1. Start the backend (`python manage.py runserver` in the backend repo). For the
   deployed API, set `url` in the environment to its Vercel URL.
2. In Bruno, choose **Open Collection**, select the `aksara` folder and pick the
   **aksara** environment.
3. Run **Accounts / Login**. It saves `token` and `refresh_token` in the environment,
   and every other request sends `Authorization: Bearer {{token}}`.

To create an account, run **Accounts / Register**, copy `uid` and the `token` from the
link in the backend terminal into `uid` and `email_token`, then run **Accounts / Verify email**.

Requests that create something save its id (`bookId`, `listingId`, ...) for the next
requests. You can also set the ids in the environment.

## Layout

```
aksara/
  bruno.json
  collection.bru          bearer auth for every request, getting-started docs
  environments/aksara.bru url, test account, ids; token and refresh_token are secrets
  Health/                 liveness check
  Accounts/               sign-up, email verification, sign-in, passwords, profile
  Books/                  catalogue and ISBN lookup
  Listings/               listings and their images
  Exchanges/              exchange requests and meetup locations
  Chat/                   conversations and messages (the app polls them)
```

The docs tab of each folder and request explains the fields, rules and responses.
