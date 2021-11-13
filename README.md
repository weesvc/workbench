# WeeSVC Workbench
Project containing scripts for perform benchmarks and compliance checks for _WeeSVC_ implementations.


## API Compliance
In order for proper comparison, each service **MUST** adhere to a strict API. API compliance is ensured using a [compliance test script](scripts/api-compliance.js) using [k6](https://k6.io/).

To target the appropriate service, the script allows for the following optional inputs:
| Input    | Description                                  | Default     |
| ---      | ---                                          |---          |
| PROTOCOL | Protocol to access the service being tested. | `http`      |
| HOST     | Hostname for the targeted service.           | `localhost` |
| PORT     | Port for the targeted service.               | `80`        |

Using the `-e` argument to pass in the script inputs as described in the [documentation](https://k6.io/docs/using-k6/environment-variables/#passing-environment-variables-to-the-k6-script). For example:

```
k6 run -e PORT=9092 scripts/api-compliance.js
```
