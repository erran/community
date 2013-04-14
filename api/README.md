# ThreatAgent API
For advanced usage see the API wiki
[page](https://github.com/threatagent/community/wiki/api).
The ThreatAgent API includes the following calls:

## API clients:
* The [ThreatAgent Gem](https://github.com/threatagent/threatagent)
* The [ThreatAgent iOS app](https://github.com/ipwnstuff/threatagent-ios)

## API calls:
* `GET /api/v1/info`
* `GET /api/v1/drone/results`
* `GET /api/v1/drone/status`
* `GET /api/v1/drone/launch`

In the case of an error you'll receive a response like the following:
```json
{
    "error": "This is a descriptive error."
}
```

---

`GET /api/v1/info`:
```json
{
  "plan": "Free",
  "drone_queries": [
    {
      "company": "Acme",
      "id": 1,
      "domain": "acme.co",
      "created_at": "2013-04-12T03:34:47Z",
      "updated_at": "2013-04-12T03:34:47Z"
    }
  ]
}
```

`GET /api/v1/drone/launch`:
```json
{
    "status": "Queued"
}
```

`GET /api/v1/status`:
```json
[
    {
        "company": "Qualys",
        "domain": "qualys.com",
        "status": "Done",
        "created_at": "2013-04-12T03:33:04Z",
        "updated_at": "2013-04-12T03:34:47Z"
    }
]
```

`GET /api/v1/drone/results`:
```json
[
    {
        "company": "Acme",
        "domain": "acme.co",
        "results": {
            "domains": {
                "acme.co": {
                    "www": "1.2.3.4"
                }
            },
            "domain": "acme.co",
            "hostnames": {
                "www": "1.2.3.4"
            },
            "company": "Acme",
            "geo_hosts": [
                {
                    "request": "www.acme.co",
                    "ip": "1.2.3.4",
                    "country_code2": "US",
                    "country_code3": "USA",
                    "country_name": "United States",
                    "continent_code": "NA",
                    "region_name": "CA",
                    "city_name": "Mountain View",
                    "postal_code": "94043",
                    "latitude": 37.41919999999999,
                    "longitude": -122.0574,
                    "dma_code": 807,
                    "area_code": 650,
                    "timezone": "America/Los_Angeles"
                }
            ],
            "address_whois": {
                "parts": [
                    {
                        "body": "",
                        "host": "1.2.3.4"
                    }
                ],
                "server": {
                    "type": "ipv4",
                    "allocation": "0.0.0.0/1",
                    "host": "",
                    "options": {},
                    "buffer": []
                },
                "content": ""
            },
            "domain_whois": "",
            "search_results": {
                "http://acme.co": "Acme Corp"
            },
            "emails": [],
            "pgp_emails": {
                "Wile E. Coyote": "wilecoyote@acme.co"
            },
            "shodan": {
                "total": 1,
                "matches": [
                    {
                        "ip": "1.2.3.4",
                        "port": 22,
                        "updated": "24.01.2013",
                        "data": "OpenSSH 1.99"
                    }
                ]
            },
            "detect": {
                "byod": false,
                "cloudflare": false,
                "exchange": false,
                "google_apps": false,
                "owa": false,
                "sharepoint": false
            },
            "shodan_names": {
                "1.2.3.4": "acme.co"
            },
            "humans": [],
            "generated_emails": [
                [
                    {
                        "firstlast": {
                          "name": "Bugs Bunny",
                          "username":"bugsbunny",
                          "domain":"@acme.co",
                          "headline":"Comedian at Warner Brothers Studios"
                        }
                    }
                ]
            ],
            "attack_surface": 1,
            "success_rating": 1
        },
        "created_at": "2013-04-12T04:08:20Z",
        "updated_at": "2013-04-12T04:08:20Z"
    }
]
```
