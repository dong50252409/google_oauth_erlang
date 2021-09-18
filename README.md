#### Erlang Google OAuth 2.0 API client to generate API token for Google S2S requests

### How to use with rebar3:

You can use `google_oauth` as a dependency in your rebar.config:

```
{deps , [
    {google_oauth, {git, "https://github.com/dong50252409/google_oauth", {branch, "master"}}}
]}.
```

### Request Token

```
{ok, Result} = google_oauth:get_access_token("service_account_file_path.json", SCOPE)

Result = 
#{
        access_token    => binary()
        expires_in      => integer() :: seconds, :: < 3600
        token_type      => binary() :: <<"Bearer">>
}
```

for push notification

```
google_oauth:get_access_token("service_account_file_path.json", <<"https://www.googleapis.com/auth/firebase.messaging">>)
```
