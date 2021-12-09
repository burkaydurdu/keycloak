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
[Keycloak - Identity and Access Management for Modern Applications](https://www.amazon.com/Keycloak-Management-Applications-protocols-applications/dp/1800562497)