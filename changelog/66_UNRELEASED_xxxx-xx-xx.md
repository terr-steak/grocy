- Stock entry labels get now also printed on inventory (only when adding products, same option "Stock entry label" like on the purchase page)
- Added a separate status filter and table row highlighting (blue) on the chores, tasks and batteries overview pages for items due today
  - Additionally, the "due soon" days of chores/tasks/batteries (top right corner settings menu) can be set to `0` to disable that filter/highlighting
- Optimized relative time display (also fixed a phrasing problem for some languages, e.g. Hungarian) (thanks @Tallyrald)
- When using LDAP authentication, the configured `LDAP_UID_ATTR` is now used to compare if the user already exists instead of the username entered on the login page (that prevents creating multiple users if you entere the username in different notations) (thanks @FloSet)
- When using reverse proxy authentication (`ReverseProxyAuthMiddleware`), it's now also possible to pass the username in an environment variable instead of an HTTP header (new `config.php` option `REVERSE_PROXY_AUTH_USE_ENV`) (thanks @Forceu)
- Performance improvements (page loading time) of the recipes page
- Fixed that stock entry labels on purchase were printed, even when "No label" was selected (was only a problem when running label printer WebHooks server side)
- Fixed that when adding missing recipe ingredients, with the option "Only check if any amount is in stock" enabled, to the shopping list, unit conversions (if any) weren't considered
- Fixed that the meal plan showed the total calories per recipe (instead of per serving as stated by the suffix)
- Fixed that formatted (HTML) text for the (hidden by default) product description column on the stock overview page was not correctly displayed
- Fixed that numeric and date-time sorting of table columns on the stock entries page did not work correctly (thanks @MasterofJOKers)
- Fixed that the barcode lookup for the "Stock by-barcode" API endpoints was case sensitive
- Fixed that the logout button/menu was missing when using external authentication (e.g. LDAP)
- Fixed that the consume page/dialog wasn't properly initialized when opening it from the stock entries page
- Fixed that entries for not existing users were missing on the stock journal
- Fixed that when having a Task without a due date, the iCal export was broken
- The API endpoint `/stock/shoppinglist/clear` has now a new optional request body parameter `done_only` (to only remove done items from the given shopping list, defaults to `false`)
