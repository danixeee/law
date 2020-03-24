# DC Council test auth repo

## Generate instructions

1. Run `oll utils startpartner` command and modify `repositories.json` and modify/replace `appveyor.yml` if necessary. See https://gist.github.com/danixeee/62b72008ac2a1e07614a500a8b897d82

2. Create (and modify if needed) *keys.json* file:

    ```json
    {
        "roles": {
            "root": {
                "number": 2,
                "threshold": 1
            },
            "targets": {
                "number": 1,
                "threshold": 1,
                "delegations": {
                    "law": {
                        "paths": [
                            "cityofsanmateo/law-xml",
                            "cityofsanmateo/law-html",
                            "cityofsanmateo/law-xml-codified",
                            "capstone",
                            "branch"
                        ],
                        "number": 1,
                        "threshold": 1,
                        "terminating": true
                    },
                    "docs":{
                        "paths": [
                            "cityofsanmateo/law-docs"
                        ],
                        "number": 1,
                        "threshold": 1,
                        "terminating": true
                    },
                    "assets":{
                        "paths": [
                            "cityofsanmateo/law-static-assets"
                        ],
                        "number": 1,
                        "threshold": 1,
                        "terminating": true
                    }
                }
            },
            "snapshot": {},
            "timestamp": {}
      },
      "keystore": "law/keystore"
    }
    ```

3. Create initial metadata: `taf repo create .\cityofsanmateo-law --keys-description keys.json --keystore .\keystore\  --test`

4. **Commit changes**

5. Commit & push
