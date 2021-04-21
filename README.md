# supabase/cli gives non functional service role key

I wonder why this did not come up yet. The service role key seems not to be the right one. When I try to run this command in the shell:

```
curl -X POST 'http://localhost:8888/auth/v1/signup' \
-H "apikey: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJzdXBhYmFzZSIsImlhdCI6MTYwMzk2ODgzNCwiZXhwIjoyNTUwNjUzNjM0LCJyb2xlIjoic2VydmljZV9yb2xlIn0.necIJaiP7X2T2QjGeV-FhpkizcNTX8HjDDBAxpgQTEI" \
-H "Content-Type: application/json" \
-d '{
  "email": "someone@email.com",
  "password": "fbgRMNOJMcQfAjlHywOr"
}'
```

I get this response

```
{
  "message":"Invalid authentication credentials"
}
```

Also when I run the script within this repo `node index.mjs` I get the same error.

The JWT_SECRET (super-secret-jwt-token-with-at-least-32-characters-long) is indeed the one that was used to sign this key, but something seems to be missing?


