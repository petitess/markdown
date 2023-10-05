Varje subscription får 3 grupper (Reader, Contributor, Owner). Grupperna ska användas för att tilldela behörigheter till samtliga teams. Behörigheter skall inte tilldelas direkt på subscriptions. Undantag från den regeln blir när man ska tilldela en special behörighet, t.ex. Key Vault Administrator.

Produktionsmiljön använder PIM (Contributor och Owner). Dev- och stagemiljön får active assigment.  

Ett exempel:

```mermaid
flowchart TD
B[mg-landingzones-01]
B-->C["sub-infra-dev-01
Active assignment"]
B-->D["sub-infra-stg-01
Active assignment"]
B-->E["sub-infra-prod-01
PIM"]

C --> F["grp-rbac-sub-infra-dev-01-Reader
    grp-rbac-sub-infra-dev-01-Contributor
    grp-rbac-sub-infra-dev-01-Owner"]

D --> G["grp-rbac-sub-infra-stg-01-Reader
    grp-rbac-sub-infra-stg-01-Contributor
    grp-rbac-sub-infra-stg-01-Owner"]

E --> H["grp-rbac-sub-infra-prod-01-Reader
    grp-rbac-sub-infra-prod-01-Contributor(PIM)
    grp-rbac-sub-infra-prod-01-Owner(PIM)"]

F --> I["
grp-team-01
user01
user02
"]

G --> J["
grp-team-01
user01
user02
"]

H --> K["
grp-team-01
user01
user02
"]
```
