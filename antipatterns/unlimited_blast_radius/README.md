## Unlimited blast radius

Lack of strict boundaries between components 

### How to detect

Check trust boundaries.

### Reasons

* Fast growing service
* Monolith's legacy

### Consequences

* Compromising one component compromise others
* Hidden dependencies

### Examples

#### Monolith

First example of an unlimited blast radius antipattern is a monolyth application with a lot of modules. The vulnerability in any of these modules leads to compromising whole application.

#### Cloud account overcrowding

Cloud account overcrowding exists when several services or environments (development, testing, production) share one cloud account.

#### Shared secrets

Multiple services share same secret. It increase risk of leaking this secret.

### How to avoid

* Separation & Isolation
