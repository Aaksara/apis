# BookX API

[Bruno](https://www.usebruno.com/) collection for the
[BookX backend](https://github.com/Aaksara/backend): every endpoint with an example
request, its rules and its responses.

## Use it

1. Start the backend (`docker compose up` in the backend repo).
2. In Bruno, choose **Open Collection**, select this folder and pick the **Local** environment.
3. Run **Auth / Login**. Bruno keeps the session cookies, so the other requests are
   signed in. To create an account, run **Auth / Register**, copy `uid` and `token` from
   the link in the backend log into the environment, then run **Auth / Verify email**.

Requests that create something save its id (`bookId`, `listingId`, ...) for the next
requests. You can also set the ids in the environment.

## Layout

```
Health/      liveness check
Auth/        sign-up, email verification, sign-in, passwords, profile
Books/       catalogue and ISBN lookup
Listings/    listings and their images
Exchanges/   exchange requests and meetup locations
Chat/        conversations and messages (folder docs cover the WebSockets)
environments/Local.bru
```

The docs tab of each folder and request explains the fields, rules and responses.
