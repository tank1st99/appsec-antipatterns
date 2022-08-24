## Insecure by default

The contract offers non-secure defaults or makes unclear assumptions about the calling code. The consumer has to make efforts for secure usage. 

### How to detect

What assumptions do we have about data, caller code, etc.?

### Reasons

* Provide "easy" way to request/call for all cases via hidden complexity

### Consequences

* Prone to vulnerabilities

### Examples

#### Direct Internet Access

All services have direct access to the Internet. Attacker could use this access to exploit different vulnerabilities. 

#### "Allow by default" policy

The access control police allows invoke handlers without annotation for users without any role. If developer forgets to explicit put annotation on handler handler will be accessible for anonymous user. It leads to access control vulnerabilities.

```python
@role(role.MODERATOR)
def moderatorHandler(params):
    pass

@role(role.ADMIN)
def adminHandler(params):
    pass

# A handler without explicit decorators is equivalent to a handler allowed for everyone
def anotherSecretHandler(params):
    pass
```

#### Implicit features

Another example of insecure by default anti-patterns is implicit enabling features. Such features may be root cause of different security vulnerabillities. Perfect example of such implicit feature is Java XML parsing libraries with enabling external entities by default.

```java
SAXParserFactory factory = SAXParserFactory.newInstance();
// to be compliant, completely disable DOCTYPE declaration:
factory.setFeature("http://apache.org/xml/features/disallow-doctype-decl", true);
```

### How to avoid

* Defaults should be safe for use
* Explicit is better than implicit
* __Deny by default__. The principle by which users and other entities are denied access unless specifically authorised.
