## Security by obscurity

Security is based on fact that attacker doesn't know implementation details.

### How to detect

For each service's component ask question: _What happens if this component will be compromised?_

### Reasons

* Lack of full knowledge about platform

### Consequences

* Reverse engineering can find way to bypass security controls 

### Examples

#### Client side controls

Implementing security controls in the mobile app, not on the server side.

#### Using WAF instead of real patching

TODO

### How to avoid

* Always implement controls on server side
