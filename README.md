# KEYCLOAK
Keycloak is an open source Identity and Access Management solution aimed at modern applications and services.
It makes it easy to secure applications and services with little to no code.
[About](https://www.keycloak.org/about)

## Parts of Keycloak

### Realm
> Think of a **realm** as a tenant. A realm is fully isolated from other realms,
it has its own configuration and its own set of applications and users.
This allows a single installation of Keycloak to be used for multiple purposes.
For example, you may want to have one realm for internal applications and employees,
and another realm for external applications and customers.

### Client
> Clients are entities that can request Keycloak to authenticate a user.
Most often, clients are applications and services that want to use 
Keycloak to secure themselves and provide a single sign-on solution.
Clients can also be entities that just want to request identity
information or an access token so that they can securely invoke other
services on the network that are secured by Keycloak.

### Client Scopes
> When a client is registered, you must define protocol mappers and role scope mappings for that client.
It is often useful to store a client scope, to make creating new clients easier by sharing some common
settings. This is also useful for requesting some claims or roles to be conditionally based on the value of
the scope parameter. Keycloak provides the concept of a client scope for this.

## Authorization

- First of all you should create role: ``Roles > Add Role``
- You go to relevant ``client`` and Click the **Authorization** tab.
- You should create ``Authorization Scopes``, For example **scopes:create**, **scopes:viewer**, **scopes:update**
- You should create ``Policies``, For example **editor**, **viewer**, **editor or viewer**,
    - You must select type **role** then you should select a role when you are creating scope.
- You should create ``Resources``, For example **res:categories**
    - You have to select scopes **create, viewer, update**
- You should create ``Permissions``, For example **category-create**, **category-view**
    - You have to select **Scope-Based**
    - You must select **resource**, **scope**, **policy**

## Dockerize
```
docker-compose up -d
```
``Admin Username: user``</br>
``Admin Password: bitnami ``

### Kubernetes
```
kubectl apply -f keycloak.yml
```

## References
[Keycloak - Identity and Access Management for Modern Applications](https://www.amazon.com/Keycloak-Management-Applications-protocols-applications/dp/1800562497) </br>
[Keycloak Official Web Site](https://www.keycloak.org)