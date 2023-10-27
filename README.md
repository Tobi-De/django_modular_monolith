# Django Modular Monolith (WIP)


example:
- core
- accounts
  - accounts_customers
  - accounts_retailers
- carts
- orders
  - orders_checkout
- products
  - products_categories
  - products_variants
  - products_catalog (Internal)
- shipping
- Inventory (internal)
- comments
  - comments_moderation (internal)
- payments
  - payments_providers
    - payments_providers_stripe
    - payments_providers_stripe
  - payments_invoices
- reports

https://youtu.be/NsHo-kThlqI?si=s4jtVHMIgdg0zlDi

- every new feature is a new app
- apps are nested 
- multi par features can be spli into multiple apps
- prefix child app name by parent name (django app names are flat)
- per app templates (default django structure)
- per app api.py file for the public api of each app
- models.py and urlpatterns (?) are considered part of the public api
- apps can depends on their parents
- apps should try not to depend too much on their child app's API 
- top level apps can depend on other top level apps
- custom properties on AppConfig (ex: internal = True)
- use django autodiscovery for some custom processing, ex: get all "reports" files in all apps list them in the UI
- enable and disable some apps (django-flags ?)