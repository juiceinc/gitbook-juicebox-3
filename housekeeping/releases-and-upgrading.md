# Releases and Upgrading

## 3.41.4[¶]()

* \[[JB-2612](https://juiceanalytics.atlassian.net/browse/JB-2612)\] **Improvement** Values in JBO table are not aligning correctly in columns
* \[[JB-2654](https://juiceanalytics.atlassian.net/browse/JB-2654)\] **Bug** update ganesha-integration code to not use credstash

## 3.41.3[¶]()

* \[[JB-2618](https://juiceanalytics.atlassian.net/browse/JB-2618)\] **Bug** Searching in the side panel for paginated slices does not work
* \[[JB-2655](https://juiceanalytics.atlassian.net/browse/JB-2655)\] **Bug** Packaging broken in py3
* \[[OPS-1772](https://juiceanalytics.atlassian.net/browse/OPS-1772)\] **Improvement** Get structlog working in prod

## 3.41.2[¶]()

* \[[JB-2643](https://juiceanalytics.atlassian.net/browse/JB-2643)\] **Bug** Avoid generating slugs over 30 characters long which can break apps.

## 3.41.1[¶]()

* \[[JB-2613](https://juiceanalytics.atlassian.net/browse/JB-2613)\] **Bug** Trend label is not showing metric label. Instead, showing metric name.
* \[[JB-2644](https://juiceanalytics.atlassian.net/browse/JB-2644)\] **Bug** GraphQL mutations should use database transactions
* \[[JB-2645](https://juiceanalytics.atlassian.net/browse/JB-2645)\] **Bug** Paginated slices raising an exception when searching

## 3.40.8[¶]()

* \[[JB-2617](https://juiceanalytics.atlassian.net/browse/JB-2617)\] **Bug** Side Panel: Date dropdowns all appear selected… but shouldn’t until selected

## 3.40.7[¶]()

* \[[JB-2604](https://juiceanalytics.atlassian.net/browse/JB-2604)\] **Bug** Python3 Anonymizer bug when anonymizers run in hstm environment

## 3.40.6[¶]()

* \[[JB-2605](https://juiceanalytics.atlassian.net/browse/JB-2605)\] **Bug** Filters\(selections\) carried over from another stack are not applied to lazy loading slices

## 3.40.5[¶]()

* Fix unicode error in the admin when showing groups
* Don’t set default ingredient format if not defined, this fixes a formatting bug in Trend slices.
* \[[JB-2602](https://juiceanalytics.atlassian.net/browse/JB-2602)\] **Improvement** Allow lazyloaded slices to skip calculating total\_count

## 3.40.4[¶]()

* \[[JB-2600](https://juiceanalytics.atlassian.net/browse/JB-2600)\] **Bug** trend ranged\_day renderer has a typo bug preventing it from working
* \[[OPS-1759](https://juiceanalytics.atlassian.net/browse/OPS-1759)\] **Task** Get new Py3 HSTM QA Environment Running

## 3.40.3[¶]()

* \[[JB-2545](https://juiceanalytics.atlassian.net/browse/JB-2545)\] **Bug** For slices with pagination, the current selection is not restored from user hash
* \[[JB-2575](https://juiceanalytics.atlassian.net/browse/JB-2575)\] **Bug** date formatting in JBO doesn’t seem to be working, the format is not included in response metadata
* \[[OPS-1759](https://juiceanalytics.atlassian.net/browse/OPS-1759)\] **Task** Get new Py3 HSTM QA Environment Running

## 3.40.2[¶]()

* \[[JB-2599](https://juiceanalytics.atlassian.net/browse/JB-2599)\] **Bug** “filters” “slice” doesn’t work because it sets the wrong group\_by\_type

## 3.40.0[¶]()

### New Features in 3.40.0[¶]()

* \[[JB-2530](https://juiceanalytics.atlassian.net/browse/JB-2530)\] CSV uploading HTTP endpoint
* \[[JB-2559](https://juiceanalytics.atlassian.net/browse/JB-2559)\] Implement Layout Picker header tool
* \[[JB-2561](https://juiceanalytics.atlassian.net/browse/JB-2561)\] Implement “filter slice” editor
* \[[JB-2562](https://juiceanalytics.atlassian.net/browse/JB-2562)\] Implement map slice editor
* \[[JB-2563](https://juiceanalytics.atlassian.net/browse/JB-2563)\] Implement trend slice editor

### Improvements in 3.40.0[¶]()

* \[[JB-2557](https://juiceanalytics.atlassian.net/browse/JB-2557)\] YAML editing ui for data sources and ingredients
* \[[JB-2558](https://juiceanalytics.atlassian.net/browse/JB-2558)\] Remove non-pertinent header tools from story editor
* \[[JB-2560](https://juiceanalytics.atlassian.net/browse/JB-2560)\] Ninebox editor improvements
* \[[JB-2568](https://juiceanalytics.atlassian.net/browse/JB-2568)\] Add juicebox role to ingredients definition so that frontend can filter dimensions by role
* \[[JB-2579](https://juiceanalytics.atlassian.net/browse/JB-2579)\] Trend editor should filter dimensions based on role
* \[[JB-2580](https://juiceanalytics.atlassian.net/browse/JB-2580)\] Map editor should filter dimensions based on role
* \[[JB-2552](https://juiceanalytics.atlassian.net/browse/JB-2552)\] Add tours on JB4

### Bugs in 3.40.0[¶]()

* \[[OPS-1750](https://juiceanalytics.atlassian.net/browse/OPS-1750)\] hashr not working in deployed containers

## 3.39.2[¶]()

* \[[\`JB-2535\`\_]()\] **Bug** Sticky filter pills are sticking to stories that have no global filters
* \[[\`JB-2542\`\_]()\] **Bug** Side panel Select All and Deselect All don’t seem to work when MinSelections and MaxSelections are set
* \[[\`JB-2549\`\_]()\] **Bug** Trend slice displayed as pill is not working correctly
* \[[\`JB-2570\`\_]()\] **Bug** django REST serializers must explicitly list fields
* \[[OPS-1752](https://juiceanalytics.atlassian.net/browse/OPS-1752)\] **Bug** Preverity reports that query logging is not working with pagination

## 3.39.0[¶]()

### New Features in 3.39.0[¶]()

* \[[JB-2435](https://juiceanalytics.atlassian.net/browse/JB-2435)\] Make the whole header sticky
* \[[JB-2488](https://juiceanalytics.atlassian.net/browse/JB-2488)\] New base templates
* \[[JB-2517](https://juiceanalytics.atlassian.net/browse/JB-2517)\] Explore using tachyons + css3 variables for themes
* \[[JB-2529](https://juiceanalytics.atlassian.net/browse/JB-2529)\] S3-notification lambda function that uploads a file to BigQuery
* \[[JB-2531](https://juiceanalytics.atlassian.net/browse/JB-2531)\] Add dataservice performance metrics to slice debug info
* \[[OPS-1723](https://juiceanalytics.atlassian.net/browse/OPS-1723)\] Make devlandia use the fruition.settings.contained settings module

### Improvements in 3.39.0[¶]()

* \[[JB-2437](https://juiceanalytics.atlassian.net/browse/JB-2437)\] The user tools dropdown trigger should only show user avatar
* \[[JB-2500](https://juiceanalytics.atlassian.net/browse/JB-2500)\] LoadAppView API endpoint should return full formatted logs on success and failure
* \[[JB-2501](https://juiceanalytics.atlassian.net/browse/JB-2501)\] Don’t reload apps one by one in dbsetup.sh script
* \[[JB-2508](https://juiceanalytics.atlassian.net/browse/JB-2508)\] Create a map renderer flavor that renders a map using a “Place” enriched dimension
* \[[JB-2510](https://juiceanalytics.atlassian.net/browse/JB-2510)\] Polish the card chrome UI
* \[[JB-2512](https://juiceanalytics.atlassian.net/browse/JB-2512)\] Add “++” buttons for adding cards
* \[[JB-2520](https://juiceanalytics.atlassian.net/browse/JB-2520)\] Enable multiple active quick selects in side panel
* \[[JB-2526](https://juiceanalytics.atlassian.net/browse/JB-2526)\] Evaluate and enable the django-structlog middleware
* \[[JB-2528](https://juiceanalytics.atlassian.net/browse/JB-2528)\] Show tracebacks in default log output
* \[[JB-2537](https://juiceanalytics.atlassian.net/browse/JB-2537)\] JBO Editor: Miscellaneous improvements
* \[[OPS-1643](https://juiceanalytics.atlassian.net/browse/OPS-1643)\] Make it possible to QA bugfixes to old releases with slots

### Bugs in 3.39.0[¶]()

* \[[JB-2493](https://juiceanalytics.atlassian.net/browse/JB-2493)\] fetchmissingjuiceboxapps does not honor draft apps
* \[[JB-2536](https://juiceanalytics.atlassian.net/browse/JB-2536)\] 504 errors when attempting to download usage reports
* \[[JB-2540](https://juiceanalytics.atlassian.net/browse/JB-2540)\] heatmap renderer is broken \(newrender\_heatmap takes exactly 4 arguments\)
* \[[JB-2554](https://juiceanalytics.atlassian.net/browse/JB-2554)\] Sticky header: when the Editor is open, and the header is sticky, it is too wide
* \[[JB-2556](https://juiceanalytics.atlassian.net/browse/JB-2556)\] The filter bar for apps with the old header does not “stick” any more

## 3.38.5[¶]()

* \[[\`JB-2535\`\_]()\] **Bug** Sticky filter pills are sticking to stories that have no global filters
* \[[\`JB-2549\`\_]()\] **Bug** Trend slice displayed as pill is not working correctly
* \[[OPS-1752](https://juiceanalytics.atlassian.net/browse/OPS-1752)\] **Bug** Preverity reports that query logging is not working with pagination

## 3.38.3[¶]()

* \[[JB-2495](https://juiceanalytics.atlassian.net/browse/JB-2495)\] **Bug** Distribution bucket displays large numbers as black, ignoring the config settings

## 3.38.2[¶]()

* \[[JB-2540](https://juiceanalytics.atlassian.net/browse/JB-2540)\] **Bug** heatmap renderer is broken \(newrender\_heatmap takes exactly 4 arguments\)
* \[[JB-2541](https://juiceanalytics.atlassian.net/browse/JB-2541)\] **Bug** Side Panel List does not play nicely with non-string values

## 3.38.1[¶]()

* \[[JB-2440](https://juiceanalytics.atlassian.net/browse/JB-2440)\] **New Feature** Don’t show the global filters or saved filters button. This feature was intended to be released in 3.38.
* \[[JB-2472](https://juiceanalytics.atlassian.net/browse/JB-2472)\] **Bug** Story loads at the bottom of the page when using the story-chooser
* **Bug** Fix permission rules not being registered.
* **Bug** Fix system check errors showing up.

## 3.38.0[¶]()

### New Features in 3.38.0[¶]()

* \[[JB-1983](https://juiceanalytics.atlassian.net/browse/JB-1983)\] clicking a Quick Select button should select the associated items
* \[[JB-2430](https://juiceanalytics.atlassian.net/browse/JB-2430)\] Data service support for quickselect which returns original data set marked with what is selected by the quickselect
* \[[JB-2434](https://juiceanalytics.atlassian.net/browse/JB-2434)\] Add a new config to the app that can be used to turn on the new header in place of the current one
* \[[JB-2442](https://juiceanalytics.atlassian.net/browse/JB-2442)\] Header color should default to theme primary color if header\_background\_css is not set
* \[[JB-2454](https://juiceanalytics.atlassian.net/browse/JB-2454)\] fetchjuiceboxapp should support fetching git branches
* \[[JB-2481](https://juiceanalytics.atlassian.net/browse/JB-2481)\] Make a jb command to upload data in an app
* \[[JB-2487](https://juiceanalytics.atlassian.net/browse/JB-2487)\] Add another tab to the outliner that has the new story outliner editor
* \[[JB-2489](https://juiceanalytics.atlassian.net/browse/JB-2489)\] Implement a BigQuery DataSource
* \[[OPS-1691](https://juiceanalytics.atlassian.net/browse/OPS-1691)\] Upgrade Session Security App in Django
* \[[OPS-1695](https://juiceanalytics.atlassian.net/browse/OPS-1695)\] Set up an HSTM devlandia environment based on fruition’s code base

### Improvements in 3.38.0[¶]()

* \[[JB-2429](https://juiceanalytics.atlassian.net/browse/JB-2429)\] Minimal header Redesign
* \[[JB-2443](https://juiceanalytics.atlassian.net/browse/JB-2443)\] Side Panel: update top position and max-height to account for available height.
* \[[JB-2459](https://juiceanalytics.atlassian.net/browse/JB-2459)\] Get the test harness working so we can run a single unit test in py3
* \[[JB-2461](https://juiceanalytics.atlassian.net/browse/JB-2461)\] MapRenderer should take parameters indicating which ingredients are which
* \[[JB-2465](https://juiceanalytics.atlassian.net/browse/JB-2465)\] Rename quickfilters as quickselects in recipe and internal
* \[[JB-2470](https://juiceanalytics.atlassian.net/browse/JB-2470)\] Allow story chooser carryForwardGlobalFilters to be adjustable
* \[[JB-2475](https://juiceanalytics.atlassian.net/browse/JB-2475)\] Implement a profiling lambda
* \[[JB-2484](https://juiceanalytics.atlassian.net/browse/JB-2484)\] Add html comment to interstitial page for monitors to detect it
* \[[JB-2490](https://juiceanalytics.atlassian.net/browse/JB-2490)\] Allow python data services to use data sources
* \[[JB-2494](https://juiceanalytics.atlassian.net/browse/JB-2494)\] Remove special treatment of apps directory and old storages approaches
* \[[OPS-1700](https://juiceanalytics.atlassian.net/browse/OPS-1700)\] Add an opslord command to deploy draft apps
* \[[OPS-1703](https://juiceanalytics.atlassian.net/browse/OPS-1703)\] Migrate Secrets Stored in Contained.py to AWS parameter store

## 3.37.2[¶]()

* \[[JB-2377](https://juiceanalytics.atlassian.net/browse/JB-2377)\] **Bug** Filter Pills Do Not Work in IE 11
* \[[JB-2485](https://juiceanalytics.atlassian.net/browse/JB-2485)\] **Bug** Embedding issue if case of email address sent to Juice does not match case of email address on Juice side

## 3.37.1[¶]()

* \[[JB-2453](https://juiceanalytics.atlassian.net/browse/JB-2453)\] **Improvement** Improve startup speed by improving discussion group calculation
* \[[JB-2466](https://juiceanalytics.atlassian.net/browse/JB-2466)\] **Bug** Free-form templates are not rendering correctly in jb4

## 3.37.0[¶]()

### New Features in 3.37.0[¶]()

* \[[JB-2357](https://juiceanalytics.atlassian.net/browse/JB-2357)\] Create schema and editor for the Measure chooser slice
* \[[JB-2390](https://juiceanalytics.atlassian.net/browse/JB-2390)\] Add graphql to list images available in app\_assets/app.id
* \[[JB-2392](https://juiceanalytics.atlassian.net/browse/JB-2392)\] User can add dimension ingredient through the editor
* \[[JB-2393](https://juiceanalytics.atlassian.net/browse/JB-2393)\] User can add measure ingredient through the editor
* \[[JB-2394](https://juiceanalytics.atlassian.net/browse/JB-2394)\] Create editor for the Dimension chooser slice. Provide it as an option in the dropdown so the user can add one to the story
* \[[JB-2395](https://juiceanalytics.atlassian.net/browse/JB-2395)\] User can add a table slice through the editor
* \[[JB-2397](https://juiceanalytics.atlassian.net/browse/JB-2397)\] Create editor for the Ninebox slice. Provide it as an option in the dropdown so the user can add it to the story
* \[[JB-2398](https://juiceanalytics.atlassian.net/browse/JB-2398)\] Create editor for the Leaderboard slice. Provide it as an option in the dropdown so the user can add it to the story
* \[[OPS-1669](https://juiceanalytics.atlassian.net/browse/OPS-1669)\] Set up Containerized QA Environment for HSTM

### Improvements in 3.37.0[¶]()

* \[[JB-2350](https://juiceanalytics.atlassian.net/browse/JB-2350)\] Option-chooser button flavor: improve data-driven service to list ingredients instead of hard-coded list
* \[[JB-2388](https://juiceanalytics.atlassian.net/browse/JB-2388)\] When preprocessing the app, prefix each background image with /app\_assets/{app.id}
* \[[JB-2389](https://juiceanalytics.atlassian.net/browse/JB-2389)\] Remove make\_background\_styles for jb4 apps
* \[[JB-2391](https://juiceanalytics.atlassian.net/browse/JB-2391)\] Evaluate logo storage in jb4
* \[[JB-2401](https://juiceanalytics.atlassian.net/browse/JB-2401)\] Improve card body content in editor
* \[[JB-2407](https://juiceanalytics.atlassian.net/browse/JB-2407)\] Validate slice config for Freeform slice
* \[[JB-2408](https://juiceanalytics.atlassian.net/browse/JB-2408)\] Validate slice config for Table slice
* \[[JB-2414](https://juiceanalytics.atlassian.net/browse/JB-2414)\] Add an option chooser renderer flavor to add quick-selects
* \[[JB-2422](https://juiceanalytics.atlassian.net/browse/JB-2422)\] Data driven data services don’t give SQL debug info
* \[[JB-2426](https://juiceanalytics.atlassian.net/browse/JB-2426)\] Store our app & stack schemas in YAML files

### Bugs in 3.37.0[¶]()

* \[[JB-2421](https://juiceanalytics.atlassian.net/browse/JB-2421)\] Side panel can bounce-animate when the mouse is positioned at side of screen
* \[[JB-2424](https://juiceanalytics.atlassian.net/browse/JB-2424)\] Automatic filters aren’t handled correctly in LoggingServiceBase or datadriven
* \[[JB-2425](https://juiceanalytics.atlassian.net/browse/JB-2425)\] jb4 Templates aren’t being saved :blush:

### Tasks in 3.37.0[¶]()

* \[[JB-2334](https://juiceanalytics.atlassian.net/browse/JB-2334)\] Merge create-student-group command back into fruition
* \[[JB-2335](https://juiceanalytics.atlassian.net/browse/JB-2335)\] validation of recipes and processors at app/stack load-time
* \[[JB-2418](https://juiceanalytics.atlassian.net/browse/JB-2418)\] re-juiceify anonymizers.py

## 3.36.4[¶]()

* \[[JB-2376](https://juiceanalytics.atlassian.net/browse/JB-2376)\] **Bug** Option chooser: button flavor ddds throws error when no items are selected
* \[[JB-2419](https://juiceanalytics.atlassian.net/browse/JB-2419)\] **Bug** Juicebox 4 global filters python service is not using the correct python import path

## 3.36.3[¶]()

* \[[JB-2370](https://juiceanalytics.atlassian.net/browse/JB-2370)\] **Bug** Trend: correct the ordering of selection tooltips

## 3.36.2[¶]()

* \[[JB-2372](https://juiceanalytics.atlassian.net/browse/JB-2372)\] **Bug** “Can’t Connect” alert isn’t realizing the connection is back

## 3.36.1[¶]()

* \[[JB-2386](https://juiceanalytics.atlassian.net/browse/JB-2386)\] **Bug** Phantom Pills from previously viewed stack are appearing in the filter bar
* \[[JB-2417](https://juiceanalytics.atlassian.net/browse/JB-2417)\] **Bug** Servicebasev4 is not cleaning up sessions appropriately

## 3.36.0[¶]()

### New Features in 3.36.0[¶]()

* \[[JB-1982](https://juiceanalytics.atlassian.net/browse/JB-1982)\] Show quick select buttons when they are present in the response for the side panel
* \[[JB-2157](https://juiceanalytics.atlassian.net/browse/JB-2157)\] Pre-loading animation for lazily loaded slices
* \[[JB-2353](https://juiceanalytics.atlassian.net/browse/JB-2353)\] Define schema format and use it to drive a form generator
* \[[JB-2355](https://juiceanalytics.atlassian.net/browse/JB-2355)\] Create schema and editor for the table slice
* \[[JB-2356](https://juiceanalytics.atlassian.net/browse/JB-2356)\] Create schema and editor for the Ranked List slice
* \[[JB-2358](https://juiceanalytics.atlassian.net/browse/JB-2358)\] Create schema and editor for ingredients \(dimension and measure\)
* \[[JB-2384](https://juiceanalytics.atlassian.net/browse/JB-2384)\] Disallow login through the login page when certain attributes exist in user extra

### Improvements in 3.36.0[¶]()

* \[[JB-2288](https://juiceanalytics.atlassian.net/browse/JB-2288)\] Add select all/deselect all buttons under the search input
* \[[JB-2323](https://juiceanalytics.atlassian.net/browse/JB-2323)\] Add cachability control to internal recipe
* \[[JB-2332](https://juiceanalytics.atlassian.net/browse/JB-2332)\] Side Panel: animates out too quickly, making it disappear immediately but should slide out.
* \[[JB-2359](https://juiceanalytics.atlassian.net/browse/JB-2359)\] Display slice group\_by\_type and slug in the slice card representation in the GUI
* \[[JB-2362](https://juiceanalytics.atlassian.net/browse/JB-2362)\] Backend support for inlined slice group backgrounds
* \[[JB-2363](https://juiceanalytics.atlassian.net/browse/JB-2363)\] Frontend support for inlined slice group backgrounds
* \[[JB-2369](https://juiceanalytics.atlassian.net/browse/JB-2369)\] Send quickselects in ingredient metadata.

### Bugs in 3.36.0[¶]()

* \[[JB-2343](https://juiceanalytics.atlassian.net/browse/JB-2343)\] our SES email sending isn’t working on jb-containers
* \[[JB-2347](https://juiceanalytics.atlassian.net/browse/JB-2347)\] Slices not being deleted through the GUI

## 3.35.5[¶]()

* \[[JB-2386](https://juiceanalytics.atlassian.net/browse/JB-2386)\] **Bug** Phantom Pills from previously viewed stack are appearing in the filter bar
* \[[JB-2417](https://juiceanalytics.atlassian.net/browse/JB-2417)\] **Bug** Servicebasev4 is not cleaning up sessions appropriately

## 3.35.4[¶]()

* \[[JB-2377](https://juiceanalytics.atlassian.net/browse/JB-2377)\] **Bug** Filter Pills Do Not Work in IE 11

## 3.35.0[¶]()

### New Features in 3.35.0[¶]()

* \[[JB-2234](https://juiceanalytics.atlassian.net/browse/JB-2234)\] Recipe-based benchmarking in data-driven data-services
* \[[JB-2283](https://juiceanalytics.atlassian.net/browse/JB-2283)\] Add a flag to Juicebox user that when TRUE prevents the user from logging in via the juiceboxdata.com URL
* \[[JB-2289](https://juiceanalytics.atlassian.net/browse/JB-2289)\] Ability to embed slice pill views in dunderscore templates

### Improvements in 3.35.0[¶]()

* \[[JB-2270](https://juiceanalytics.atlassian.net/browse/JB-2270)\] Refactor side panel list views
* \[[JB-2298](https://juiceanalytics.atlassian.net/browse/JB-2298)\] Unify Side Panel Range Views
* \[[JB-2300](https://juiceanalytics.atlassian.net/browse/JB-2300)\] List item number values: apply metadata formatting and invert color to white on selection.
* \[[JB-2308](https://juiceanalytics.atlassian.net/browse/JB-2308)\] Enable the polyfills provided by babel-present-env
* \[[JB-2303](https://juiceanalytics.atlassian.net/browse/JB-2303)\] Don’t generate bad SQL when an automatic filter list contains None.
* \[[JB-2314](https://juiceanalytics.atlassian.net/browse/JB-2314)\] Improve renderer configurability for JBO use cases

### Bugs in 3.35.0[¶]()

* \[[JB-2293](https://juiceanalytics.atlassian.net/browse/JB-2293)\] Downloads don’t work on public apps
* \[[JB-2342](https://juiceanalytics.atlassian.net/browse/JB-2342)\] group\_by\_type in ‘date’ renderer breaking filters
* \[[JB-2371](https://juiceanalytics.atlassian.net/browse/JB-2371)\] Side Panel: after hitting “Sort”, the list items are disappearing

## 3.34.3[¶]()

* \[[JB-2336](https://juiceanalytics.atlassian.net/browse/JB-2336)\] **Bug** Issue loading logos in apps in deployed environments
* \[[JB-2341](https://juiceanalytics.atlassian.net/browse/JB-2341)\] **Bug** Since 404 error fix deployed, Client query logging excludes users logging in through embedded site

## 3.34.2[¶]()

* \[[JB-2340](https://juiceanalytics.atlassian.net/browse/JB-2340)\] **Bug** Make default anonymization of Juicebox ingredients only anonymize strings
* **Bug** Update recipe to 0.6.2 to fix a bug with using ingredients.yaml files that included DivideMetric and other deprecated ingredients.
* **Bug** Pin imgix requirement.

## 3.34.1[¶]()

* \[[JB-2282](https://juiceanalytics.atlassian.net/browse/JB-2282)\] **Bug** Add `has_powerbar_access` property to UserShim model
* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue - \[[JB-2333](https://juiceanalytics.atlassian.net/browse/JB-2333)\] **Bug** slice-group-{slug} class on group divs has disappeared - **Bug** Recipe generating non-serializable output was blocking app loading.
>
> > Fixed in Recipe 0.6.1

## 3.34.0[¶]()

### New Features in 3.34.0[¶]()

* \[[JB-2224](https://juiceanalytics.atlassian.net/browse/JB-2224)\] Text-based data source/ingredient creation for an app
* \[[JB-2241](https://juiceanalytics.atlassian.net/browse/JB-2241)\] Add api endpoint to get, create and update an app’s data sources and ingredients
* \[[JB-2269](https://juiceanalytics.atlassian.net/browse/JB-2269)\] slice groups in slice groups need support in the frontend

### Improvements in 3.34.0[¶]()

* \[[JB-2250](https://juiceanalytics.atlassian.net/browse/JB-2250)\] Update draft loading POC to enable fetch and load of juicebox 3 draft apps
* \[[JB-2255](https://juiceanalytics.atlassian.net/browse/JB-2255)\] For JB4, update option-chooser button flavor button styles to look like new pills
* \[[JB-2262](https://juiceanalytics.atlassian.net/browse/JB-2262)\] Range selection improvements
* \[[JB-2266](https://juiceanalytics.atlassian.net/browse/JB-2266)\] Keep editor open \(and in the same view\) after hitting “save” btn
* \[[JB-2267](https://juiceanalytics.atlassian.net/browse/JB-2267)\] Make the editor panel its own div container outside the entire stack
* \[[JB-2268](https://juiceanalytics.atlassian.net/browse/JB-2268)\] Make the text area fill available height
* \[[OPS-1633](https://juiceanalytics.atlassian.net/browse/OPS-1633)\] dynamically create “slot” task definitions and run them as tasks

### Bugs in 3.34.0[¶]()

* \[[JB-2265](https://juiceanalytics.atlassian.net/browse/JB-2265)\] JB v4: lazy-loading error when using data yaml
* \[[JB-2299](https://juiceanalytics.atlassian.net/browse/JB-2299)\] App Loading through jb API fails silently
* \[[JB-2304](https://juiceanalytics.atlassian.net/browse/JB-2304)\] wide slice groups aren’t rendering properly since nested slice groups were added

### Tasks in 3.34.0[¶]()

* \[[JB-2295](https://juiceanalytics.atlassian.net/browse/JB-2295)\] Copy hstm files to core verbatim
* \[[JB-2296](https://juiceanalytics.atlassian.net/browse/JB-2296)\] Delete Jenkins.HSTM
* \[[JB-2297](https://juiceanalytics.atlassian.net/browse/JB-2297)\] Move over hstm-specific settings variables
* \[[JB-2301](https://juiceanalytics.atlassian.net/browse/JB-2301)\] Switch from mocha-phantomjs to mocha-chrome-headless
* \[[JB-2306](https://juiceanalytics.atlassian.net/browse/JB-2306)\] Update the stacks/views.py to handle hstm-specific logic

## 3.33.9[¶]()

* \[[JB-2282](https://juiceanalytics.atlassian.net/browse/JB-2282)\] **Bug** Add `has_powerbar_access` property to UserShim model
* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue

## 3.33.8[¶]()

* \[[JB-2331](https://juiceanalytics.atlassian.net/browse/JB-2331)\] **Bug** Null values break sorting in side panel

## 3.33.7[¶]()

* \[[\`JB-2327\`\_]()\] **Bug** Users with non-dictionary extras create 500 errors for the entire app

## 3.33.6[¶]()

* \[[JB-2285](https://juiceanalytics.atlassian.net/browse/JB-2285)\] **Bug** Client is reporting embedded apps are returning 404 errors in IE
* Added support for Google BigQuery

## 3.33.5[¶]()

* \[[JB-2287](https://juiceanalytics.atlassian.net/browse/JB-2287)\] **Bug** Escape various javascript variables \(including initial selections & stack metadata\) to prevent “script” tags in JS strings from breaking the page.

## 3.33.4[¶]()

* \[[JB-2286](https://juiceanalytics.atlassian.net/browse/JB-2286)\] **Bug** Accepting invitations doesn’t work since the upgrade to django 1.11

## 3.33.3[¶]()

* \[[JB-2202](https://juiceanalytics.atlassian.net/browse/JB-2202)\] **New Feature** JB4: Themes having parents
* \[[JB-2257](https://juiceanalytics.atlassian.net/browse/JB-2257)\] **Bug** JB v4 Story-chooser: browser error breaking the stack

Note: Due to a process issue, release 3.33.1 and 3.33.2 were skipped.

## 3.33.0[¶]()

### New Features in 3.33.0[¶]()

* \[[JB-1941](https://juiceanalytics.atlassian.net/browse/JB-1941)\] Support date range selections in the side panel
* \[[JB-2156](https://juiceanalytics.atlassian.net/browse/JB-2156)\] Support sorting in the side panel
* \[[JB-2160](https://juiceanalytics.atlassian.net/browse/JB-2160)\] Hovering over an item in the list mimics hovering over it in the slice
* \[[JB-2202](https://juiceanalytics.atlassian.net/browse/JB-2202)\] JB4: Themes having parents
* \[[JB-2235](https://juiceanalytics.atlassian.net/browse/JB-2235)\] Generalized “Marker” support in data-driven data services
* \[[JB-2244](https://juiceanalytics.atlassian.net/browse/JB-2244)\] Create API endpoint to update stack based on passed yaml
* \[[JB-2245](https://juiceanalytics.atlassian.net/browse/JB-2245)\] Text area to edit stack

### Improvements in 3.33.0[¶]()

* \[[JB-2194](https://juiceanalytics.atlassian.net/browse/JB-2194)\] If `juicebox_version: "4"` set slices default config to `collapsable: false`
* \[[JB-2230](https://juiceanalytics.atlassian.net/browse/JB-2230)\] Upgrade to Django 1.11
* \[[JB-2243](https://juiceanalytics.atlassian.net/browse/JB-2243)\] Send the stack’s raw\_config to the frontend
* \[[JB-2248](https://juiceanalytics.atlassian.net/browse/JB-2248)\] Extend the length of id/slug fields to support draft apps
* \[[JB-2252](https://juiceanalytics.atlassian.net/browse/JB-2252)\] Add search icon to new pills

### Bugs in 3.33.0[¶]()

* \[[JB-2246](https://juiceanalytics.atlassian.net/browse/JB-2246)\] Pill label should update when group\_by\_type changes
* \[[JB-2259](https://juiceanalytics.atlassian.net/browse/JB-2259)\] can’t create users in develop branch since upgrade to Django 1.11.
* \[[JB-2264](https://juiceanalytics.atlassian.net/browse/JB-2264)\] Getting `'Slice' object has no attribute 'data_service_label'` when trying to `jb remove` an app
* \[[JBC-63](https://juiceanalytics.atlassian.net/browse/JBC-63)\] Unnecessary vertical scroll bar in ranked list \(IE only\)

### Tasks in 3.33.0[¶]()

* \[[OPS-1594](https://juiceanalytics.atlassian.net/browse/OPS-1594)\] Enable Encryption at rest for Elasticache

## 3.32.6[¶]()

* \[[JB-2337](https://juiceanalytics.atlassian.net/browse/JB-2337)\] **Bug** pin imgix version instead of using git master
* \[[JB-2340](https://juiceanalytics.atlassian.net/browse/JB-2340)\] **Bug** Only apply default anonymization to dimensions that return strings

## 3.32.5[¶]()

* \[[JB-2282](https://juiceanalytics.atlassian.net/browse/JB-2282)\] **Bug** Add `has_powerbar_access` property to UserShim model
* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue

## 3.32.4[¶]()

* \[[JB-2261](https://juiceanalytics.atlassian.net/browse/JB-2261)\] **Bug** Header is not displayed in embed views when show\_header is passed

## 3.32.3[¶]()

* \[[JB-2238](https://juiceanalytics.atlassian.net/browse/JB-2238)\] **Bug** Lollipop labels cut off when bars are too small
* \[[JB-2258](https://juiceanalytics.atlassian.net/browse/JB-2258)\] **Bug** `request.session` and `request.user.is_authenticated` are missing from the data service shims
* \[[OPS-1594](https://juiceanalytics.atlassian.net/browse/OPS-1594)\] **Task** Enable Encryption at rest for Elasticache

## 3.32.1[¶]()

* \[[JB-2254](https://juiceanalytics.atlassian.net/browse/JB-2254)\] **Bug** Packaging an app doesn’t pick up the right app version
* **Bug** Packaging juicebox\_version=4 apps failed.
* **Bug** Fix an issue with new rendering approach
* **Bug** Show full exception information on exceptions when loading juicebox apps.
* **Bug** Fix a bug in bubble renderer.
* **Bug** Fix a bug where loading juiceboxapp tried to log a message before the logger was defined.

Packaging an app doesn’t pick up the right app version

## 3.32.0[¶]()

### New Features in 3.32.0[¶]()

* \[[JB-1943](https://juiceanalytics.atlassian.net/browse/JB-1943)\] Support search in the side panel
* \[[JB-2187](https://juiceanalytics.atlassian.net/browse/JB-2187)\] Create a new endpoint for embedding a user
* \[[JB-2209](https://juiceanalytics.atlassian.net/browse/JB-2209)\] Implement a new system & YAML syntax for response renderers

### Improvements in 3.32.0[¶]()

* \[[JB-2181](https://juiceanalytics.atlassian.net/browse/JB-2181)\] In Ganesha, if case is different between the existing user account and the email address in invitation, a new invitation will be sent
* \[[JB-2186](https://juiceanalytics.atlassian.net/browse/JB-2186)\] User creation APIs should include app access
* \[[JB-2213](https://juiceanalytics.atlassian.net/browse/JB-2213)\] Move any slice selection policies from the chart plugin to a central place
* \[[JB-2214](https://juiceanalytics.atlassian.net/browse/JB-2214)\] Improve how the side panel header gets its title value
* \[[JB-2216](https://juiceanalytics.atlassian.net/browse/JB-2216)\] Add a JSONField to the Stack model to store prevalidated configuration as JSON.
* \[[JB-2119](https://juiceanalytics.atlassian.net/browse/JB-2119)\] Update webpack and babel
* \[[JB-2131](https://juiceanalytics.atlassian.net/browse/JB-2131)\] Pass in context to sankey hover templates

### Bugs in 3.32.0[¶]()

* \[[JB-2176](https://juiceanalytics.atlassian.net/browse/JB-2176)\] User handles are not unique, and users can set their handle to another user’s handle

## 3.31.5[¶]()

* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue

## 3.31.4[¶]()

* \[[JB-2142](https://juiceanalytics.atlassian.net/browse/JB-2142)\] **Bug** Image Capture Cuts off Right Side for 2/3 Style Slice
* \[[JB-2149](https://juiceanalytics.atlassian.net/browse/JB-2149)\] **Bug** Unneeded Horizontal Scroll Bars Present on Lollipop and 2/3 Width Slices
* \[[JB-2208](https://juiceanalytics.atlassian.net/browse/JB-2208)\] **Bug** Tours do not reset when switching between stacks

## 3.31.2[¶]()

* \[[JB-2142](https://juiceanalytics.atlassian.net/browse/JB-2142)\] **Bug** Image Capture Cuts off Right Side for 2/3 Style Slice
* \[[JB-2189](https://juiceanalytics.atlassian.net/browse/JB-2189)\] **Bug** Slice-Groups Removing Data Response With include\_commands
* \[[JB-2200](https://juiceanalytics.atlassian.net/browse/JB-2200)\] **Bug** JB4: Free-forms without a data service defined are showing a “No Data” error, but shouldn’t.
* \[[JB-2201](https://juiceanalytics.atlassian.net/browse/JB-2201)\] **Bug** JB4: Global filters are showing up even if they aren’t defined in stack.yaml.

## 3.31.1[¶]()

* \[[JB-2232](https://juiceanalytics.atlassian.net/browse/JB-2232)\] **Bug** Make it possible to download XLS data again

## 3.31.0[¶]()

### New Features in 3.31.0[¶]()

* \[[JB-2025](https://juiceanalytics.atlassian.net/browse/JB-2025)\] allow defining data sources in YAML
* \[[JB-2090](https://juiceanalytics.atlassian.net/browse/JB-2090)\] Create a POC for the desired permissions
* \[[JB-2155](https://juiceanalytics.atlassian.net/browse/JB-2155)\] Support hierarchical list selections in the side panel
* \[[JB-2169](https://juiceanalytics.atlassian.net/browse/JB-2169)\] Recipe-level postprocessor for adding a fixed “data collection”

### Improvements in 3.31.0[¶]()

* \[[JB-2033](https://juiceanalytics.atlassian.net/browse/JB-2033)\] Cleanup CallableDataService model and related objects
* \[[JB-2109](https://juiceanalytics.atlassian.net/browse/JB-2109)\] Slice Groups: add ability to have groups within groups
* \[[JB-2152](https://juiceanalytics.atlassian.net/browse/JB-2152)\] Filters in request bodies should be namespaced for jb4 apps
* \[[JB-2153](https://juiceanalytics.atlassian.net/browse/JB-2153)\] All selections should be automatic filter keys in DataDrivenDataServices
* \[[JB-2159](https://juiceanalytics.atlassian.net/browse/JB-2159)\] Provide an app’s JB version to frontend
* \[[JB-2167](https://juiceanalytics.atlassian.net/browse/JB-2167)\] Make DataSource app-scoped instead of client-scoped
* \[[JBC-60](https://juiceanalytics.atlassian.net/browse/JBC-60)\] Add subtitle option to `layout: default`
* \[[JBC-61](https://juiceanalytics.atlassian.net/browse/JBC-61)\] Filter pill container absolute positioning
* \[[OPS-1569](https://juiceanalytics.atlassian.net/browse/OPS-1569)\] App Testing Proof of Concept
* \[[JBC-18](https://juiceanalytics.atlassian.net/browse/JBC-18)\] Default anonymization for JB3 built-in ingredients
* \[[OPS-1561](https://juiceanalytics.atlassian.net/browse/OPS-1561)\] devlandia docker images should be based on the production docker image
* \[[OPS-1563](https://juiceanalytics.atlassian.net/browse/OPS-1563)\] use pip-compile for fruition

### Bugs in 3.31.0[¶]()

* \[[JB-2146](https://juiceanalytics.atlassian.net/browse/JB-2146)\] FruitionUser.uid is not unique
* \[[JB-2158](https://juiceanalytics.atlassian.net/browse/JB-2158)\] List selection doesn’t update properly for min/max selections

## 3.30.8[¶]()

* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue

## 3.30.7[¶]()

* \[[JB-2142](https://juiceanalytics.atlassian.net/browse/JB-2142)\] **Bug** Image Capture Cuts off Right Side for 2/3 Style Slice
* \[[JB-2149](https://juiceanalytics.atlassian.net/browse/JB-2149)\] **Bug** Unneeded Horizontal Scroll Bars Present on Lollipop and 2/3 Width Slices
* \[[JB-2208](https://juiceanalytics.atlassian.net/browse/JB-2208)\] **Bug** Tours do not reset when switching between stacks

## 3.30.5[¶]()

* \[[JB-2149](https://juiceanalytics.atlassian.net/browse/JB-2149)\] **Bug** Unneeded Horizontal Scroll Bars Present on Lollipop and 2/3 Width Slices

## 3.30.4[¶]()

* \[[JB-2182](https://juiceanalytics.atlassian.net/browse/JB-2182)\] **Bug** Bubble renderer is not handling UnicodeEncodeError
* **Bug** Add yet more fields to ShimUser

## 3.30.3[¶]()

* \[[JB-2180](https://juiceanalytics.atlassian.net/browse/JB-2180)\] **Bug** Add more fields to ShimUser

## 3.30.2[¶]()

* \[[JB-2175](https://juiceanalytics.atlassian.net/browse/JB-2175)\] **Bug** Add ShimRequest.path

## 3.30.1[¶]()

* \[[JB-2064](https://juiceanalytics.atlassian.net/browse/JB-2064)\] **Bug** Story chooser: `style` defaults stopped showing up, but did before.
* \[[JB-2132](https://juiceanalytics.atlassian.net/browse/JB-2132)\] **Improvement** Convert data service fields to data service object
* \[[JB-2148](https://juiceanalytics.atlassian.net/browse/JB-2148)\] **Bug** IE Is not displaying labels for bubble slice
* \[[JB-2172](https://juiceanalytics.atlassian.net/browse/JB-2172)\] **Bug** Empty Global Filters slice is included in response when no data service defined

## 3.30.0[¶]()

### New Features in 3.30.0[¶]()

* \[[JB-1939](https://juiceanalytics.atlassian.net/browse/JB-1939)\] Add side panel styling and improve to show and close as needed
* \[[JB-1942](https://juiceanalytics.atlassian.net/browse/JB-1942)\] Support selections in the side panel
* \[[JB-2056](https://juiceanalytics.atlassian.net/browse/JB-2056)\] Change Stack model to have service details
* \[[JB-2085](https://juiceanalytics.atlassian.net/browse/JB-2085)\] Support data-driven dataservices
* \[[JB-2092](https://juiceanalytics.atlassian.net/browse/JB-2092)\] support specifying pre-processors and post-processors for slices in YAML
* \[[JB-2117](https://juiceanalytics.atlassian.net/browse/JB-2117)\] Add react to the frontend and create a sidebar that will hold the outline editor
* \[[JB-2130](https://juiceanalytics.atlassian.net/browse/JB-2130)\] syntax for specifying dynamic ingredients that are based on request params
* \[[OPS-1499](https://juiceanalytics.atlassian.net/browse/OPS-1499)\] automate building UVA AMIs with Packer in Jenkins

### Improvements in 3.30.0[¶]()

* \[[JB-2111](https://juiceanalytics.atlassian.net/browse/JB-2111)\] Improve anonymizers to use seeded faker generators
* \[[JB-2132](https://juiceanalytics.atlassian.net/browse/JB-2132)\] Convert data service fields to data service object
* \[[JB-2115](https://juiceanalytics.atlassian.net/browse/JB-2115)\] Investigate and implement changes to Ganesha
* \[[JB-2139](https://juiceanalytics.atlassian.net/browse/JB-2139)\] Make heatmap layer show up in Image download
* \[[OPS-1523](https://juiceanalytics.atlassian.net/browse/OPS-1523)\] set up the snapshots service for containerized JB deployments
* \[[JBC-57](https://juiceanalytics.atlassian.net/browse/JBC-57)\] Option-chooser: When `maxSelections: 0`, disable hover effects

### Bugs in 3.30.0[¶]()

* \[[JB-2107](https://juiceanalytics.atlassian.net/browse/JB-2107)\] Don’t chdir while fetching juicebox apps
* \[[JB-2112](https://juiceanalytics.atlassian.net/browse/JB-2112)\] Jenkins deployment of Juicebox should wait for the deployment and check for errors

## 3.29.9[¶]()

* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue

## 3.29.8[¶]()

* \[[JB-2142](https://juiceanalytics.atlassian.net/browse/JB-2142)\] **Bug** Image Capture Cuts off Right Side for 2/3 Style Slice
* \[[JB-2149](https://juiceanalytics.atlassian.net/browse/JB-2149)\] **Bug** Unneeded Horizontal Scroll Bars Present on Lollipop and 2/3 Width Slices
* \[[JB-2208](https://juiceanalytics.atlassian.net/browse/JB-2208)\] **Bug** Tours do not reset when switching between stacks

## 3.29.6[¶]()

* \[[JB-2182](https://juiceanalytics.atlassian.net/browse/JB-2182)\] **Bug** Bubble renderer is not handling UnicodeEncodeError

## 3.29.5[¶]()

* \[[JB-2148](https://juiceanalytics.atlassian.net/browse/JB-2148)\] **Bug** IE Is not displaying labels for bubble slice

## 3.29.4[¶]()

* \[[JB-2150](https://juiceanalytics.atlassian.net/browse/JB-2150)\] **Bug** Heatmap not appearing in image downloads

## 3.29.3[¶]()

* \[[JB-2139](https://juiceanalytics.atlassian.net/browse/JB-2139)\] **Improvement + Bug** Make heatmap layer show up in Image download
* \[[\`JB-2144\`\_]()\] **Bug** Sticky filters tour appears mostly off screen

## 3.29.2[¶]()

* \[[JB-2114](https://juiceanalytics.atlassian.net/browse/JB-2114)\] **Bug** int\(\) argument must be a string or a number, not ‘SimpleLazyObject’
* \[[JB-2140](https://juiceanalytics.atlassian.net/browse/JB-2140)\] **Bug** Issue with table data downloads

## 3.29.1[¶]()

* \[[JB-2114](https://juiceanalytics.atlassian.net/browse/JB-2114)\] **Bug** When non-logged in users attempted to access a story that had discussions, a server error was being generated.

## 3.29.0[¶]()

### New Features in 3.29.0[¶]()

* \[[JB-1940](https://juiceanalytics.atlassian.net/browse/JB-1940)\] Display the slice’s data as a list in the side panel
* \[[JB-2053](https://juiceanalytics.atlassian.net/browse/JB-2053)\] Load juicebox\_version=4 file format

### Improvements in 3.29.0[¶]()

* \[[JB-2063](https://juiceanalytics.atlassian.net/browse/JB-2063)\] Throw bug warning when a slice gets assigned a fixture service that isn’t present.
* \[[JB-2075](https://juiceanalytics.atlassian.net/browse/JB-2075)\] Remove My Apps button when user only has access to 1 app
* \[[JB-2082](https://juiceanalytics.atlassian.net/browse/JB-2082)\] juicebox-cli and juicebox-public-api need to handle client- specific auth
* \[[JB-2097](https://juiceanalytics.atlassian.net/browse/JB-2097)\] Change data service storage from separate fields to a JSONField
* \[[JB-2098](https://juiceanalytics.atlassian.net/browse/JB-2098)\] Fix backgrounds on jb4 loads
* \[[JB-2099](https://juiceanalytics.atlassian.net/browse/JB-2099)\] Fix fixture data in juicebox 4 loads

### Bugs in 3.29.0[¶]()

* \[[JB-2064](https://juiceanalytics.atlassian.net/browse/JB-2064)\] Story chooser: `style` defaults stopped showing up, but did before.
* \[[JB-2110](https://juiceanalytics.atlassian.net/browse/JB-2110)\] If a slice has “collapsed: true” in its saved state, and the slice is uncollapsible, it will never appear

### Tasks in 3.29.0[¶]()

* \[[JB-2093](https://juiceanalytics.atlassian.net/browse/JB-2093)\] Bring in hstm user tools menu dropdown to core

## 3.28.10[¶]()

* \[[JB-2207](https://juiceanalytics.atlassian.net/browse/JB-2207)\] **Bug** Bubble slice: Values overlap in bubbles for zoom in/out

> IE issue

## 3.28.9[¶]()

* \[[JB-2142](https://juiceanalytics.atlassian.net/browse/JB-2142)\] **Bug** Image Capture Cuts off Right Side for 2/3 Style Slice
* \[[JB-2149](https://juiceanalytics.atlassian.net/browse/JB-2149)\] **Bug** Unneeded Horizontal Scroll Bars Present on Lollipop and 2/3 Width Slices

## 3.28.7[¶]()

* \[[JB-2182](https://juiceanalytics.atlassian.net/browse/JB-2182)\] **Bug** Bubble renderer is not handling UnicodeEncodeError

## 3.28.6[¶]()

* \[[JB-2148](https://juiceanalytics.atlassian.net/browse/JB-2148)\] **Bug** IE Is not displaying labels for bubble slice

## 3.28.5[¶]()

* \[[JB-2064](https://juiceanalytics.atlassian.net/browse/JB-2064)\] **Bug** Story chooser: `style` defaults stopped showing up, but did before.

## 3.28.4[¶]()

* \[[JB-2114](https://juiceanalytics.atlassian.net/browse/JB-2114)\] **Bug** When non-logged in users attempted to access a story that had discussions, a server error was being generated.

## 3.28.3[¶]()

* \[[JB-2114](https://juiceanalytics.atlassian.net/browse/JB-2114)\] **Bug** int\(\) argument must be a string or a number, not ‘SimpleLazyObject’

## 3.28.2[¶]()

* \[[JB-2110](https://juiceanalytics.atlassian.net/browse/JB-2110)\] **Bug** If a slice has “collapsed: true” in its saved state, and the slice is uncollapsible, it will never appear
* \[[OPS-1500](https://juiceanalytics.atlassian.net/browse/OPS-1500)\] **Task** Adds additional information \(filters, user permissions, query delimiters\) to query logs

## 3.28.0[¶]()

### New Features in 3.28.0[¶]()

* \[[JB-1929](https://juiceanalytics.atlassian.net/browse/JB-1929)\] Refactor service base to support lazy loading
* \[[JB-1939](https://juiceanalytics.atlassian.net/browse/JB-1939)\] Add side panel styling and improve to show and close as needed
* \[[JB-1995](https://juiceanalytics.atlassian.net/browse/JB-1995)\] Create app asset collection function
* \[[JB-2024](https://juiceanalytics.atlassian.net/browse/JB-2024)\] Define DataSource model object
* \[[JB-2059](https://juiceanalytics.atlassian.net/browse/JB-2059)\] Improve embed urls with customizable embed duration and redirect location for invalid urls

### Improvements in 3.28.0[¶]()

* \[[JB-1944](https://juiceanalytics.atlassian.net/browse/JB-1944)\] New Pill: Updated tooltip design
* \[[JB-2044](https://juiceanalytics.atlassian.net/browse/JB-2044)\] User email address should be unique within a client, not across clients
* \[[JB-2078](https://juiceanalytics.atlassian.net/browse/JB-2078)\] Update APIs that retrieve resources based on user email to use the client as a filter
* \[[JB-2086](https://juiceanalytics.atlassian.net/browse/JB-2086)\] Patch /api/v1/api-token-auth/ for jb-cli

### Bugs in 3.28.0[¶]()

* \[[JB-2022](https://juiceanalytics.atlassian.net/browse/JB-2022)\] Bubble slice’s root node unexpectedly gets selected by JuiceBox
* \[[JB-2057](https://juiceanalytics.atlassian.net/browse/JB-2057)\] Creating a discussion post on a details table slice causes a snapshot error
* \[[JB-2091](https://juiceanalytics.atlassian.net/browse/JB-2091)\] Slice Drawer doesn’t disable button after input field validation

## 3.27.3[¶]()

* \[[JB-2058](https://juiceanalytics.atlassian.net/browse/JB-2058)\] **Bug** The “Password expiration days” Client configuration option is not working

## 3.27.2[¶]()

* \[[JB-2057](https://juiceanalytics.atlassian.net/browse/JB-2057)\] **Bug** Creating a discussion post on a details table slice causes a snapshot error
* \[[JB-2060](https://juiceanalytics.atlassian.net/browse/JB-2060)\] **Bug** Loading apps generates large app.metadata values
* \[[JB-2069](https://juiceanalytics.atlassian.net/browse/JB-2069)\] **Bug** JB 3.22 change to remove [selectionType](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/templates.html#selectiontype) from global filters not backwards compatible for v2 apps

## 3.27.0[¶]()

### New Features in 3.27.0[¶]()

* \[[JB-1931](https://juiceanalytics.atlassian.net/browse/JB-1931)\] Add ‘include-data’ lazy-loading flag to request params
* \[[JB-1935](https://juiceanalytics.atlassian.net/browse/JB-1935)\] Add front-end flag allowing slices to lazily load data
* \[[JB-1945](https://juiceanalytics.atlassian.net/browse/JB-1945)\] New Pill: Filtering counting up and down
* \[[JB-1946](https://juiceanalytics.atlassian.net/browse/JB-1946)\] New Pill: Icon defaults for ingredients.yaml
* \[[OPS-1468](https://juiceanalytics.atlassian.net/browse/OPS-1468)\] Set up staging and prod containerized environments
* \[[JBC-32](https://juiceanalytics.atlassian.net/browse/JBC-32)\] Add postprocessor decorator to filter result rows

### Improvements in 3.27.0[¶]()

* \[[JB-1969](https://juiceanalytics.atlassian.net/browse/JB-1969)\] Add marker layer to maps
* \[[JB-1976](https://juiceanalytics.atlassian.net/browse/JB-1976)\] Show results of app load in powerbar in front-end
* \[[JB-1987](https://juiceanalytics.atlassian.net/browse/JB-1987)\] Allow for users to be added to multiple apps within a Client in Ganesha
* \[[JB-1993](https://juiceanalytics.atlassian.net/browse/JB-1993)\] New Pill: Set max-width to 200px with ‘…’ for long labels.
* \[[JB-1998](https://juiceanalytics.atlassian.net/browse/JB-1998)\] Remove remaining boto2 references in core code, replace with boto3
* \[[JB-2005](https://juiceanalytics.atlassian.net/browse/JB-2005)\] Save the classes defined in slice.style to the slice and list them in apis
* \[[JB-2006](https://juiceanalytics.atlassian.net/browse/JB-2006)\] Apply slice styles as classes on the slice container
* \[[JB-2008](https://juiceanalytics.atlassian.net/browse/JB-2008)\] Change the default email sending user to a no-reply email
* \[[JB-2009](https://juiceanalytics.atlassian.net/browse/JB-2009)\] Convert the existing slice extra css to a css class that is applied via slice.style
* \[[JB-2010](https://juiceanalytics.atlassian.net/browse/JB-2010)\] Convert built in slice.style code to css classes
* \[[JB-2038](https://juiceanalytics.atlassian.net/browse/JB-2038)\] Add the requirements.txt to use Athena in SQLAlchemy
* \[[JB-1956](https://juiceanalytics.atlassian.net/browse/JB-1956)\] Allow build\_recipe to return “bound, renderable SQLAlchemy queries”
* \[[JB-1991](https://juiceanalytics.atlassian.net/browse/JB-1991)\] Embedded slices use token authentication
* \[[JB-2019](https://juiceanalytics.atlassian.net/browse/JB-2019)\] Modified append\_response\_item\_collections to accept multiple additional responses

### Tasks in 3.27.0[¶]()

* \[[JB-1992](https://juiceanalytics.atlassian.net/browse/JB-1992)\] Test existing embeds with token auth

## 3.26.4[¶]()

* \[[JB-2057](https://juiceanalytics.atlassian.net/browse/JB-2057)\] Creating a discussion post on a details table slice causes a snapshot error
* \[[JB-2069](https://juiceanalytics.atlassian.net/browse/JB-2069)\] JB 3.22 change to remove [selectionType](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/templates.html#selectiontype) from global filters not backwards compatible for v2 apps

## 3.26.2[¶]()

* \[[JB-2017](https://juiceanalytics.atlassian.net/browse/JB-2017)\] **Bug** if no dataservice is defined in a slice config, **do not** automatically apply the story chooser fixture

## 3.26.1[¶]()

* \[[JB-2021](https://juiceanalytics.atlassian.net/browse/JB-2021)\] **Bug** Bubble slice renderer creates ids based on dimension names not dimension ids
* \[[OPS-1482](https://juiceanalytics.atlassian.net/browse/OPS-1482)\] **Bug** Extreme Slowness and errors in HSTM apps containing Map Slice

## 3.26.0[¶]()

### New Features in 3.26.0[¶]()

* \[[JB-1931](https://juiceanalytics.atlassian.net/browse/JB-1931)\] Add ‘include-data’ lazy-loading flag to request params
* \[[JB-1933](https://juiceanalytics.atlassian.net/browse/JB-1933)\] Display slices with a filter pill even when nothing is selected
* \[[JB-1934](https://juiceanalytics.atlassian.net/browse/JB-1934)\] Display slices without a filter pill using [display\_slice\_as](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/common_configuration.html#display-slice-as)
* \[[JB-1964](https://juiceanalytics.atlassian.net/browse/JB-1964)\] Display slices with the new filter pill when [display\_slice\_as](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/common_configuration.html#display-slice-as) is set to “default”
* \[[JB-1974](https://juiceanalytics.atlassian.net/browse/JB-1974)\] Add renderer flavor for map markers

### Improvements in 3.26.0[¶]()

* \[[JB-1958](https://juiceanalytics.atlassian.net/browse/JB-1958)\] When new pill config is used, new pills should show in sticky bar
* \[[JB-1959](https://juiceanalytics.atlassian.net/browse/JB-1959)\] Allow user permissions for Client Admins to be modified in Ganesha
* \[[JB-1960](https://juiceanalytics.atlassian.net/browse/JB-1960)\] Allow Ganesha users to modify their own user permissions
* \[[JB-1966](https://juiceanalytics.atlassian.net/browse/JB-1966)\] Add a utility function to get data collections by name
* \[[JB-1968](https://juiceanalytics.atlassian.net/browse/JB-1968)\] Add heatmap layer to maps
* \[[JB-1971](https://juiceanalytics.atlassian.net/browse/JB-1968)\] Add renderer flavor for heatmap
* \[[JB-1975](https://juiceanalytics.atlassian.net/browse/JB-1975)\] Fix jb start blowing up if any initial app loads fail
* \[[JB-1976](https://juiceanalytics.atlassian.net/browse/JB-1976)\] Show results of app load in powerbar in front-end
* \[[OPS-1452](https://juiceanalytics.atlassian.net/browse/OPS-1452)\] add an option for using nginx instead of s3 for static files
* \[[OPS-1453](https://juiceanalytics.atlassian.net/browse/OPS-1453)\] Jenkins auto-deploy to dev and staging on commits to “develop” and “master”

### Bugs in 3.26.0[¶]()

* \[[JB-1909](https://juiceanalytics.atlassian.net/browse/JB-1909)\] Unable to Select and Deselect in the Search option in IE browser
* \[[JB-1985](https://juiceanalytics.atlassian.net/browse/JB-1985)\] Bubble chart labels display wrong size temporarily when zooming
* \[[JB-2007](https://juiceanalytics.atlassian.net/browse/JB-2007)\] Juicebox queries don’t generate deterministic sql code

## 3.25.4[¶]()

* \[[JB-2057](https://juiceanalytics.atlassian.net/browse/JB-2057)\] Creating a discussion post on a details table slice causes a snapshot error
* \[[JB-2069](https://juiceanalytics.atlassian.net/browse/JB-2069)\] JB 3.22 change to remove [selectionType](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/templates.html#selectiontype) from global filters not backwards compatible for v2 apps

## 3.25.3[¶]()

This release includes changes from 3.23.4 and 3.24.1

## 3.25.2[¶]()

* \[[JB-1985](https://juiceanalytics.atlassian.net/browse/JB-1985)\] **Bug** Bubble chart labels display wrong size temporarily when zooming

## 3.25.1[¶]()

* \[[JB-1984](https://juiceanalytics.atlassian.net/browse/JB-1984)\] **Bug** Restore filter pill creation policy for bare slices.

## 3.25.0[¶]()

### New Features in 3.25.0[¶]()

* \[[JB-1822](https://juiceanalytics.atlassian.net/browse/JB-1822)\] Add `icon` config option in ingredients.yaml field definitions
* \[[JB-1854](https://juiceanalytics.atlassian.net/browse/JB-1854)\] Slice Groups should allow sharing common config among all slices
* \[[JB-1903](https://juiceanalytics.atlassian.net/browse/JB-1903)\] Slice group styling with support for `wide`
* \[[JB-1929](https://juiceanalytics.atlassian.net/browse/JB-1929)\] Refactor service base to support lazy loading
* \[[JB-1932](https://juiceanalytics.atlassian.net/browse/JB-1932)\] Display slices as ONLY a pill
* \[[JB-1937](https://juiceanalytics.atlassian.net/browse/JB-1937)\] Slice groups should support backgrounds
* \[[JBC-1](https://juiceanalytics.atlassian.net/browse/JBC-1)\] Enhanced slice-inspector shows debugging info for all slices.
* \[[JB-1951](https://juiceanalytics.atlassian.net/browse/JB-1951)\] servicebasev4 allows data services to use shelf\_file and shelf\_table as a shortcut to load ingredients from yaml.

### Improvements in 3.25.0[¶]()

* \[[JB-1922](https://juiceanalytics.atlassian.net/browse/JB-1922)\] Text in Bubble Slice should wrap within the node \(bubble\)
* \[[JB-1953](https://juiceanalytics.atlassian.net/browse/JB-1953)\] Internal improvements to data services access to user data permissions.

### Bugs in 3.25.0[¶]()

* \[[JB-1936](https://juiceanalytics.atlassian.net/browse/JB-1936)\] dropdown option-choosers inside slice-groups get cut off
* \[[JB-1973](https://juiceanalytics.atlassian.net/browse/JB-1973)\] Tour bugfixes, couldn’t delete, tours were unordered, updated date was showing a warning

## 3.24.1[¶]()

* \[[JB-1909](https://juiceanalytics.atlassian.net/browse/JB-1909)\] **Bug** Unable to Select and Deselect in the Search option in IE browser
* \[[OPS-1482](https://juiceanalytics.atlassian.net/browse/OPS-1482)\] **Bug** Extreme Slowness and errors in HSTM apps containing Map Slice

## 3.24.0[¶]()

### New Features in 3.24.0[¶]()

* \[[JB-1905](https://juiceanalytics.atlassian.net/browse/JB-1905)\] Add support for new config \(default\_start\_slice\) to stack.yaml
* \[[JB-1906](https://juiceanalytics.atlassian.net/browse/JB-1906)\] Use the value of `default_start_slice` to load the story at that slice
* \[[JB-22](https://juiceanalytics.atlassian.net/browse/JB-22)\] Key Metrics Hierarchy \(Relationship\) slice is passing two objects for a single selection
* \[[JBC-22](https://juiceanalytics.atlassian.net/browse/JBC-22)\] Data service decorators

### Improvements in 3.24.0[¶]()

* \[[JB-1902](https://juiceanalytics.atlassian.net/browse/JB-1902)\] Fix the namespace used by Juicebox css from .fr- to .jb-

### Tasks in 3.24.0[¶]()

* \[[OPS-1417](https://juiceanalytics.atlassian.net/browse/OPS-1417)\] Rebuild UVA dev image from OPS-1395 issue.

## 3.23.4[¶]()

* \[[OPS-1482](https://juiceanalytics.atlassian.net/browse/OPS-1482)\] **Bug** Extreme Slowness and errors in HSTM apps containing Map Slice

## 3.23.3[¶]()

* \[[JB-1927](https://juiceanalytics.atlassian.net/browse/JB-1927)\] **Bug** Some visualizations are not centered properly.

## 3.23.2[¶]()

* \[[JB-1883](https://juiceanalytics.atlassian.net/browse/JB-1883)\] **Bug** Improve handling in commands when the user presses enter/return.
* \[[JB-1885](https://juiceanalytics.atlassian.net/browse/JB-1885)\] **Bug** If global filters minSelection is 1, the other global filters are not refreshed with that selection
* \[[JB-1886](https://juiceanalytics.atlassian.net/browse/JB-1886)\] **Bug** Selected range shown in filter pill in Trend slice does not always match the actual selection made in the slice

## 3.23.1[¶]()

* \[[JB-1875](https://juiceanalytics.atlassian.net/browse/JB-1875)\] **Improvement** Add a flag that allows users to see slice debug info.
* \[[JB-1887](https://juiceanalytics.atlassian.net/browse/JB-1887)\] **Bug** When a comparison metric is null, a benchmark bubble should not appear in the slice
* \[[JB-1889](https://juiceanalytics.atlassian.net/browse/JB-1889)\] **Bug** Download Data button not functioning in juicebox version 2 apps

### New Features in 3.23.0[¶]()

* \[[JB-1809](https://juiceanalytics.atlassian.net/browse/JB-1809)\] Add a summary row to the table slice that allows for sum and average of table columns
* \[[JB-1855](https://juiceanalytics.atlassian.net/browse/JB-1855)\] Slice groups should have a “layout” parameter
* \[[JB-1856](https://juiceanalytics.atlassian.net/browse/JB-1856)\] Allow automatic crossfiltering for slice groups
* \[[JB-1860](https://juiceanalytics.atlassian.net/browse/JB-1860)\] Add support for the story\_filter\_carryover flag in the UI
* \[[JB-1869](https://juiceanalytics.atlassian.net/browse/JB-1869)\] Support group\_layout config in the UI
* \[[JB-1870](https://juiceanalytics.atlassian.net/browse/JB-1870)\] Serialize groups when rendering stacks to the frontend

### Improvements in 3.23.0[¶]()

* \[[JB-1872](https://juiceanalytics.atlassian.net/browse/JB-1872)\] Improve recipe response renderers

### Bugs in 3.23.0[¶]()

* \[[JB-1868](https://juiceanalytics.atlassian.net/browse/JB-1868)\] Full-width slices do not resize correctly in snapshot view

## 3.22.2[¶]()

* \[[JB-1867](https://juiceanalytics.atlassian.net/browse/JB-1867)\] **Bug** NineBox renderer doesn’t account for using a third metric to size bubbles

## 3.22.0[¶]()

### New Features in 3.22.0[¶]()

* \[[JB-1661](https://juiceanalytics.atlassian.net/browse/JB-1661)\] Autoinject a story chooser slice type on the bottom of a stack
* \[[JB-1662](https://juiceanalytics.atlassian.net/browse/JB-1662)\] Story chooser slices with no data service generate a fixture using config.stories
* \[[JB-1853](https://juiceanalytics.atlassian.net/browse/JB-1853)\] Allow configuring slice groups in stack.yaml files
* \[[JB-1827](https://juiceanalytics.atlassian.net/browse/JB-1827)\] Add ability for Global Filters to force a selection. This DEPRECATES selectOne and selectMany and canReset in global filters in favor of performing selection in the same way as slices.

### Improvements in 3.22.0[¶]()

* \[[JB-1044](https://juiceanalytics.atlassian.net/browse/JB-1044)\] Disallow client admins from being changed via the client api
* \[[JB-1577](https://juiceanalytics.atlassian.net/browse/JB-1577)\] Package and Load juicebox app should store the proper data to ensure we can restore a specific app version.
* \[[JB-1578](https://juiceanalytics.atlassian.net/browse/JB-1578)\] On Juicebox startup, we should query the database for loaded apps and versions and fetch them
* \[[JB-1659](https://juiceanalytics.atlassian.net/browse/JB-1659)\] Add properties to stack model to support story switching
* \[[JB-1790](https://juiceanalytics.atlassian.net/browse/JB-1790)\] Ganesha user activity improved to only show activity on the focused app

### Bugs in 3.22.0[¶]()

* \[[JB-1587](https://juiceanalytics.atlassian.net/browse/JB-1587)\] Pagination widget was not displaying properly
* \[[JB-1747](https://juiceanalytics.atlassian.net/browse/JB-1747)\] Snapshot button getting skewed in two column view when there is a new comment
* \[[JB-1805](https://juiceanalytics.atlassian.net/browse/JB-1805)\] Images aren’t showing in HealthStream Devlandia

## 3.21.2[¶]()

Fixes from 3.20.6

## 3.21.1[¶]()

Fixes from 3.20.5

## 3.21.0[¶]()

### New Features in 3.21.0[¶]()

* \[[JB-1784](https://juiceanalytics.atlassian.net/browse/JB-1784)\] Snapshot comment should load with page when user clicks URL in email.

### Improvements in 3.21.0[¶]()

* \[[JB-1723](https://juiceanalytics.atlassian.net/browse/JB-1723)\] Make “My Apps” popup scrollable with max-height
* \[[JB-1763](https://juiceanalytics.atlassian.net/browse/JB-1763)\] Add a privacy policy link to Juicebox footers
* \[[JB-1766](https://juiceanalytics.atlassian.net/browse/JB-1766)\] Pass the DownloadDataCommand.Meta.name to the data service when running downloads
* \[[JB-1767](https://juiceanalytics.atlassian.net/browse/JB-1767)\] Add a new builtincommand for downloading data that uses unload flow
* \[[JB-1797](https://juiceanalytics.atlassian.net/browse/JB-1797)\] Update the Juicebox Invitations API to allow the creation of multiple invites at the same time

### Tasks in 3.21.0[¶]()

* \[[JB-1748](https://juiceanalytics.atlassian.net/browse/JB-1748)\] Django settings files shouldn’t have client-specific get\_secrets calls in them
* \[[JB-1788](https://juiceanalytics.atlassian.net/browse/JB-1788)\] Juicebox should set the ganesha-auth cookie as a domain-wide cookie, and name it something other than ganeshaSID
* \[[OPS-1251](https://juiceanalytics.atlassian.net/browse/OPS-1251)\] Preverity’s Redshift connection string should be added to secrets
* \[[OPS-1281](https://juiceanalytics.atlassian.net/browse/OPS-1281)\] Improve scripts/release.py

## 3.20.6[¶]()

* \[[JB-1867](https://juiceanalytics.atlassian.net/browse/JB-1867)\] **Bug** NineBox renderer doesn’t account for using a third metric to size bubbles

## 3.20.5[¶]()

* \[[JB-1747](https://juiceanalytics.atlassian.net/browse/JB-1747)\] **Bug** Snapshot btn getting skewed in two column view when there is a new comment
* \[[JB-1805](https://juiceanalytics.atlassian.net/browse/JB-1805)\] **Bug** Images aren’t showing in HealthStream Devlandia
* \[[OPS-1276](https://juiceanalytics.atlassian.net/browse/OPS-1276)\] **Improvement** Store the version number in a separate file.

## 3.20.4[¶]()

Fixes from 3.18.5

## 3.20.3[¶]()

* Fix: Add secrets for preverity

## 3.20.2[¶]()

Fixes from 3.18.4.

## 3.20.1[¶]()

Fixes from 3.18.3.

## 3.20.0[¶]()

### New Features in 3.20.0[¶]()

* \[[JB-1714](https://juiceanalytics.atlassian.net/browse/JB-1714)\] New JB endpoint to allow an authenticated JB user to log into Ganesha

### Improvements in 3.20.0[¶]()

* \[[JB-1632](https://juiceanalytics.atlassian.net/browse/JB-1632)\] Extend get\_secret to get secrets from alternate locations
* \[[JB-1729](https://juiceanalytics.atlassian.net/browse/JB-1729)\] Design: Improve footer functionality with Juicebox logo & link option.
* \[[JB-1731](https://juiceanalytics.atlassian.net/browse/JB-1731)\] Add invitation\_subject and invitation\_body to an App api detail response
* \[[JB-1732](https://juiceanalytics.atlassian.net/browse/JB-1732)\] Support custom subject and body when creating invitations
* \[[JB-1736](https://juiceanalytics.atlassian.net/browse/JB-1736)\] Update the Nine-box slice to take up the available width when not configured to do otherwise.
* \[[JB-1737](https://juiceanalytics.atlassian.net/browse/JB-1737)\] Update the Trend slice to take up the available width when not configured to do otherwise

## 3.19.3[¶]()

Fixes from 3.18.5.

## 3.19.2[¶]()

Fixes from 3.18.4.

## 3.19.1[¶]()

Fixes from 3.18.3.

## 3.19.0[¶]()

### New Features in 3.19.0[¶]()

* \[[JB-1666](https://juiceanalytics.atlassian.net/browse/JB-1666)\] Create a story-chooser frontend slice
* \[[JB-1686](https://juiceanalytics.atlassian.net/browse/JB-1686)\] Ability to customize user invitations by app

### Improvements in 3.19.0[¶]()

* \[[JB-1598](https://juiceanalytics.atlassian.net/browse/JB-1598)\] Bubble Slice: update height and width to available in container.
* \[[JB-1659](https://juiceanalytics.atlassian.net/browse/JB-1659)\] Add properties to stack model to support story switching
* \[[JB-1659](https://juiceanalytics.atlassian.net/browse/JB-1659)\] Add properties to stack model to support story switching

### Tasks in 3.19.0[¶]()

* \[[JB-1674](https://juiceanalytics.atlassian.net/browse/JB-1674)\] Turn on FullStory for TDOE’s embedded application
* \[[JB-1690](https://juiceanalytics.atlassian.net/browse/JB-1690)\] Remove UserHashs for an app in the Django admin
* \[[JB-1696](https://juiceanalytics.atlassian.net/browse/JB-1696)\] Disable Global Filter selection while filters are refreshing

## 3.18.5[¶]()

* \[[JB-1747](https://juiceanalytics.atlassian.net/browse/JB-1747)\] Snapshot btn getting skewed in two column view when there is a new comment
* \[[JB-1775](https://juiceanalytics.atlassian.net/browse/JB-1775)\] Sticky filters have scroll bar

## 3.18.4[¶]()

* \[[JB-1750](https://juiceanalytics.atlassian.net/browse/JB-1750)\] Bubble Slice headers don’t display when using Internet Explorer
* \[[JB-1770](https://juiceanalytics.atlassian.net/browse/JB-1770)\] IE: “No data” is not displayed correctly on slices

## 3.18.3[¶]()

* \[[JB-1453](https://juiceanalytics.atlassian.net/browse/JB-1453)\] BUG: Invite acceptance page showing logged in header
* \[[JB-1720](https://juiceanalytics.atlassian.net/browse/JB-1720)\] Filter text off center & white box in toolbar
* \[[JB-1749](https://juiceanalytics.atlassian.net/browse/JB-1749)\] DOM sometimes fails to update when switching stacks
* \[[JB-1759](https://juiceanalytics.atlassian.net/browse/JB-1759)\] FireFox: Pills are duplicating as you scroll
* Display Ganasha admin in all supported environments

## 3.18.2[¶]()

Fixes from 3.17.4.

## 3.18.1[¶]()

* \[[JB-1378](https://juiceanalytics.atlassian.net/browse/JB-1378)\] Trend slice line chart selected range was not resetting correctly.

## 3.18.0[¶]()

### New Features in 3.18.0[¶]()

* \[[JB-1483](https://juiceanalytics.atlassian.net/browse/JB-1483)\] For dropdowns, add options to \(a\) select all and \(b\) deselect all \(c\) configure max selections
* \[[JB-1525](https://juiceanalytics.atlassian.net/browse/JB-1525)\] Individual filters status change transitions
* \[[JB-1542](https://juiceanalytics.atlassian.net/browse/JB-1542)\] Create a new slice type `story_chooser`
* \[[JB-1667](https://juiceanalytics.atlassian.net/browse/JB-1667)\] Templates and css to support story chooser
* \[[JB-1675](https://juiceanalytics.atlassian.net/browse/JB-1675)\] Add bubble slice renderer

### Improvements in 3.18.0[¶]()

* \[[JB-1404](https://juiceanalytics.atlassian.net/browse/JB-1404)\] Repoint the Manage Users and App reporting links in fruition to ganesha
* \[[JB-1635](https://juiceanalytics.atlassian.net/browse/JB-1635)\] Use cerberus validation for app.yaml
* \[[JB-1653](https://juiceanalytics.atlassian.net/browse/JB-1653)\] Use cerberus validation for backgrounds and headers \(requires updates to apps\)
* \[[JB-1699](https://juiceanalytics.atlassian.net/browse/JB-1699)\] Upgrade Django to current 1.8 security patch

## 3.17.4[¶]()

* \[[JB-1715](https://juiceanalytics.atlassian.net/browse/JB-1715)\] Filters relating to slices that are not on the current path carry over to other stories and aren’t dismissable.

## 3.17.3[¶]()

* \[[JB-1525](https://juiceanalytics.atlassian.net/browse/JB-1525)\] Individual filters status change transitions

## 3.17.2[¶]()

Fixes from 3.16.8

## 3.17.1[¶]()

* \[[JB-1617](https://juiceanalytics.atlassian.net/browse/JB-1617)\] Date widget selectors overlap in Global Filters
* \[[JB-1708](https://juiceanalytics.atlassian.net/browse/JB-1708)\] Slices were not filtering each other due to eventmap not being set correctly

## 3.17.0[¶]()

### New Features in 3.17.0[¶]()

* \[[JB-1484](https://juiceanalytics.atlassian.net/browse/JB-1484)\] The search bar in slices can now be used to perform flexible selections.

### Improvements in 3.17.0[¶]()

* \[[JB-1604](https://juiceanalytics.atlassian.net/browse/JB-1604)\] Add animations to better show what’s going on when filters are added or removed from the filter bar
* \[[JB-1613](https://juiceanalytics.atlassian.net/browse/JB-1613)\] Search input to start searching after first character instead of the second in the nine box slice
* \[[JB-1472](https://juiceanalytics.atlassian.net/browse/JB-1472)\] Allow app authors API access \(which enables access to ganesha\)
* \[[JB-1634](https://juiceanalytics.atlassian.net/browse/JB-1634)\] Improved validation for stacks
* \[[JB-1624](https://juiceanalytics.atlassian.net/browse/JB-1624)\] Improve the layout when lots of filters are collected in the filter bar

## 3.16.8[¶]()

* \[[JB-1610](https://juiceanalytics.atlassian.net/browse/JB-1610)\] Trend slice not using custom colors in embedded apps
* \[[JB-1711](https://juiceanalytics.atlassian.net/browse/JB-1711)\] App is not usable due to global filters overlay at specific screen widths.

## 3.16.7[¶]()

* \[[JB-1684](https://juiceanalytics.atlassian.net/browse/JB-1684)\] Global filters in Portfolio spin for a long time even when the request has failed

## 3.16.6[¶]()

* \[[JB-1676](https://juiceanalytics.atlassian.net/browse/JB-1676)\] Automatically Carry Filters: sticky filters are carrying over that shouldn’t

## 3.16.5[¶]()

* \[[JB-1681](https://juiceanalytics.atlassian.net/browse/JB-1681)\] JS exception thrown sometimes while building global filter pills for the filter bar

## 3.16.4[¶]()

* \[[JB-1376](https://juiceanalytics.atlassian.net/browse/JB-1376)\] Ranked list 2 values that exceed bar length should display to right of bar
* \[[JB-1644](https://juiceanalytics.atlassian.net/browse/JB-1644)\] Snapshot image not loading in UVA-Dev or prod

## 3.16.3[¶]()

* \[[JB-1619](https://juiceanalytics.atlassian.net/browse/JB-1619)\] Fixed Leaderboard to allow numeric column labels to be used.
* \[[JB-1638](https://juiceanalytics.atlassian.net/browse/JB-1638)\] Styling of the filter pills in the filter bar is off in Juicebox 2 apps
* \[[JB-1640](https://juiceanalytics.atlassian.net/browse/JB-1640)\] Duplicate global filter pill entries when switching stacks

## 3.16.2[¶]()

* \[[JB-1589](https://juiceanalytics.atlassian.net/browse/JB-1589)\] Settings server side selection in tables wasn’t working correctly. In fact, setting selections caused every row to be selected.
* \[[JB-1628](https://juiceanalytics.atlassian.net/browse/JB-1628)\] twocolumns layout slices rearrange widgets to make things look tidy, these widget layouts weren’t exactly what we wanted, now they are.

## 3.16.1[¶]()

* \[[JB-1623](https://juiceanalytics.atlassian.net/browse/JB-1623)\] **Improvement** Add a feature tour to explain sticky filters.
* \[[JB-1626](https://juiceanalytics.atlassian.net/browse/JB-1626)\] **Fix** Layout twocolumns wasn’t working

## 3.16.0[¶]()

### New Features in 3.16.0[¶]()

* \[[JB-1514](https://juiceanalytics.atlassian.net/browse/JB-1514)\] Always carry forward global filter selections when switching between stories using the nav bar
* \[[JB-1527](https://juiceanalytics.atlassian.net/browse/JB-1527)\] Stick and Unstick Slice Filters
* \[[JB-1528](https://juiceanalytics.atlassian.net/browse/JB-1528)\] Update existing Filters
* \[[JB-1544](https://juiceanalytics.atlassian.net/browse/JB-1544)\] Add a –strict flag to loadjuiceboxapp
* \[[JB-1545](https://juiceanalytics.atlassian.net/browse/JB-1545)\] If strict flag on loading from yaml, raise validation errors as BadJuicebox
* \[[JB-1516](https://juiceanalytics.atlassian.net/browse/JB-1516)\] Add new two column slice layouts
* \[[JB-1584](https://juiceanalytics.atlassian.net/browse/JB-1584)\] New slice styling option _cover_ displays slice with full-bleed, full-height background.

### Improvements in 3.16.0[¶]()

* \[[JB-1473](https://juiceanalytics.atlassian.net/browse/JB-1473)\] Return non-cumulated 0-30/31-60/61-90 usage data as app usage.
* \[[JB-1583](https://juiceanalytics.atlassian.net/browse/JB-1583)\] Add slice top level yaml config `layout`
* \[[JB-1620](https://juiceanalytics.atlassian.net/browse/JB-1620)\] Make app version number visible on the front end
* \[[JB-1622](https://juiceanalytics.atlassian.net/browse/JB-1622)\] Make user tools a settings configurable option
* \[[JB-1508](https://juiceanalytics.atlassian.net/browse/JB-1508)\] Add a theme option to hide stack navigation tabs

## 3.15.1[¶]()

* \[[JB-1612](https://juiceanalytics.atlassian.net/browse/JB-1612)\] **Fix** Loading a hash with selections in map slice causes app crashing when no data is available from the data service.

## 3.15.0[¶]()

### Improvements in 3.15.0[¶]()

* \[[JB-1550](https://juiceanalytics.atlassian.net/browse/JB-1550)\] Convert core to use boto3 for file storages.
* \[[JB-1555](https://juiceanalytics.atlassian.net/browse/JB-1555)\] Apply precommit hooks to juicebox codebase.
* \[[JB-1585](https://juiceanalytics.atlassian.net/browse/JB-1585)\] Improve layout locations so that only components determine the size of container

## 3.14.6[¶]()

* \[[JB-1612](https://juiceanalytics.atlassian.net/browse/JB-1612)\] **Fix** Loading a hash with selections in map slice causes app crashing when no data is available from the data service.

## 3.14.5[¶]()

* \[[JB-1548](https://juiceanalytics.atlassian.net/browse/JB-1548)\] **Fix** When compiling the css needed for the inline styles in the snapshot notification email, don’t include any extraneous css like the theme’s extra css or slice styles.

## 3.14.4[¶]()

* \[[JB-1603](https://juiceanalytics.atlassian.net/browse/JB-1603)\] **Fix** Use sqlalchemy-redshift

## 3.14.3[¶]()

* \[[JB-1599](https://juiceanalytics.atlassian.net/browse/JB-1599)\] **Fix** Update sqlalchemy and psycopg2

## 3.14.2[¶]()

* \[[JB-1499](https://juiceanalytics.atlassian.net/browse/JB-1499)\] **Improvement** Automate the Juicebox release process
* \[[JB-1495](https://juiceanalytics.atlassian.net/browse/JB-1495)\] **Fix** For some users the Global Filters overlay is covering the stack, but invisible, and making the stack unusable.
* \[[JB-1549](https://juiceanalytics.atlassian.net/browse/JB-1549)\] **Fix** Stack switch renderer should generate a hash for empty global filters or slice selections
* \[[JB-1597](https://juiceanalytics.atlassian.net/browse/JB-1597)\] **Fix** Stacks that have slices configured with `guide` do not load in IE9

## 3.14.1[¶]()

* \[[JB-1532](https://juiceanalytics.atlassian.net/browse/JB-1532)\] Discussions and downloaded images would sometimes by clipped.

## 3.14.0[¶]()

### New Features in 3.14.0[¶]()

* \[[JB-1463](https://juiceanalytics.atlassian.net/browse/JB-1463)\] Juicebox apps can now use custom fonts from the Google Font API
* \[[JB-1485](https://juiceanalytics.atlassian.net/browse/JB-1485)\] Ability to invite a user as a “demo user”
* \[[OPS-911](https://juiceanalytics.atlassian.net/browse/OPS-911)\] Build API to fetch Juicebox Apps

### Improvements in 3.14.0[¶]()

* \[[JB-1455](https://juiceanalytics.atlassian.net/browse/JB-1455)\] Snapshots have been reworked to be faster and more reliable.
* \[[JB-1466](https://juiceanalytics.atlassian.net/browse/JB-1466)\] When admin pages have a background image, it doesn’t fill the background consistently.
* \[[JB-1468](https://juiceanalytics.atlassian.net/browse/JB-1468)\] Ranked list: label readability needs improvement
* \[[JB-1500](https://juiceanalytics.atlassian.net/browse/JB-1500)\] Admin pages show more details about when an app was packaged, by who, when and details about the git commit
* \[[JB-1507](https://juiceanalytics.atlassian.net/browse/JB-1507)\] Include the entire invitation object in the response to a POST request to create an invitation

### Bugs in 3.14.0[¶]()

* \[[JB-1438](https://juiceanalytics.atlassian.net/browse/JB-1438)\] Ascii codec can’t decode unicode character in EncryptedDimension
* \[[JB-1469](https://juiceanalytics.atlassian.net/browse/JB-1469)\] Filter pills: ‘x’ btn sometimes lays out weird with an extra long filter label

## 3.13.3[¶]()

* \[[JB-1498](https://juiceanalytics.atlassian.net/browse/JB-1498)\] Collectstatic failing with error about deprecated crypo hasher.
* \[[JB-1504](https://juiceanalytics.atlassian.net/browse/JB-1504)\] Public apps with snapshots not loading

## 3.13.2[¶]()

* \[[JB-1491](https://juiceanalytics.atlassian.net/browse/JB-1491)\] **Fix** JB Commands that used a form prevented a page redirection without user confirmation. Now they allow it without whinging.
* \[[JB-1492](https://juiceanalytics.atlassian.net/browse/JB-1492)\] **Fix** Download data command wasn’t working in jb2 apps.

## 3.13.1[¶]()

* \[[JB-1479](https://juiceanalytics.atlassian.net/browse/JB-1479)\] Commands for a slice would not display when switching between stacks.
* \[[JB-1380](https://juiceanalytics.atlassian.net/browse/JB-1380)\] The highlight color of the guide bars in the RankedList v2 slice was not coming through.
* \[[JB-1439](https://juiceanalytics.atlassian.net/browse/JB-1439)\] Clearing selections through the filter pill on the JBv2 Leaderboard slice was throwing a Javascript error.
* \[[JB-1481](https://juiceanalytics.atlassian.net/browse/JB-1481)\] **Fix** Apps embedded in an iframe would not load in IE.

## 3.13.0[¶]()

### Features in 3.13.0[¶]()

* \[[JB-1425](https://juiceanalytics.atlassian.net/browse/JB-1425)\] Added support to display a custom icon and label for a Juicebox command. Also added support to display a success or failure notification message upon the commands successful/unsuccessful completion.
* \[[JB-1427](https://juiceanalytics.atlassian.net/browse/JB-1427)\] Allow apps to define custom commands.
* \[[JB-1426](https://juiceanalytics.atlassian.net/browse/JB-1426)\] Added support for collecting user input for JB commands before sending it.
* \[[JB-1416](https://juiceanalytics.atlassian.net/browse/JB-1416)\] Ability to launch an app tour from a button placed anywhere in slices

### Improvements in 3.13.0[¶]()

* \[[JB-1428](https://juiceanalytics.atlassian.net/browse/JB-1428)\] Allow all commands to get full slice state details and non-expiring image url. This enables webhooks that can save slice state and full thumbnails by subclassing DownloadImageCommand.
* \[[JB-1420](https://juiceanalytics.atlassian.net/browse/JB-1420)\] Nudged global filters refresh button up so that it aligns with other pills.
* \[[JB-1437](https://juiceanalytics.atlassian.net/browse/JB-1437)\] You can now add and click on hyperlinks in the card slice and it will not interfere with the selection of the card item.
* \[[JB-1386](https://juiceanalytics.atlassian.net/browse/JB-1386)\] Add a render\_config option to set trend dataset name.
* \[[JB-1405](https://juiceanalytics.atlassian.net/browse/JB-1405)\] Add a builtin command to post to Slack that can be configured using app metadata.
* \[[JB-1450](https://juiceanalytics.atlassian.net/browse/JB-1450)\] Use webpack to bundle the vendor js into a single file
* \[[JB-1451](https://juiceanalytics.atlassian.net/browse/JB-1451)\] Allow imgix src to be configured using IMGIX\_DOMAINS
* \[[JB-1452](https://juiceanalytics.atlassian.net/browse/JB-1452)\] Remove deprecated code from django settings
* \[[JB-1461](https://juiceanalytics.atlassian.net/browse/JB-1461)\] Remove hard-coded /static/ in scss, cleanup scss cruft
* \[[JB-1382](https://juiceanalytics.atlassian.net/browse/JB-1382)\] Adjust the layout of the Ranked List slice when positive and negative values are present so that the center line is always centered.

### Fixes in 3.13.0[¶]()

* \[[JB-1429](https://juiceanalytics.atlassian.net/browse/JB-1429)\] Add a management command to clean up cached avatar images.

### Tasks in 3.13.0[¶]()

* \[[JB-1462](https://juiceanalytics.atlassian.net/browse/JB-1462)\] Stop building and publishing docs from CI/CD process

## 3.12.2[¶]()

* \[[JB-1436](https://juiceanalytics.atlassian.net/browse/JB-1436)\] JBCLWD apps were not loading

## 3.12.1[¶]()

* \[[JB-1430](https://juiceanalytics.atlassian.net/browse/JB-1430)\] Headers were being mistakenly hidden on help pages

## 3.12.0[¶]()

### Features in 3.12.0[¶]()

* \[[JB-1322](https://juiceanalytics.atlassian.net/browse/JB-1322)\] Perform app usage reporting with SQL query using eventlog\_log table. Usage reporting supports variable time windows. Client api app responses return usage data.
* \[[JB-1323](https://juiceanalytics.atlassian.net/browse/JB-1323)\] Add an endpoint to get user usage data in the client api. This will be visible in Ganesha.
* \[[JB-1419](https://juiceanalytics.atlassian.net/browse/JB-1419)\] Create a simplified view for taking snapshots that only includes the snapshot content.
* \[[JB-1351](https://juiceanalytics.atlassian.net/browse/JB-1351)\] New default Lollipop renderer supports custom grouping, configurable matching of comparison metrics, custom targets, even change the name of the Benchmark!
* \[[JB-1396](https://juiceanalytics.atlassian.net/browse/JB-1396)\] Add expiring tokens that can be used for API authentication.
* \[[JB-1408](https://juiceanalytics.atlassian.net/browse/JB-1408)\] Allow client admins to request one-time use embedding links for any of their managed users. These links can be used to embed an app in an iframe.

### Improvements in 3.12.0[¶]()

* \[[JB-1395](https://juiceanalytics.atlassian.net/browse/JB-1395)\] New users can be created using the client api. Previously, we had only supported creating new invitations.

## 3.11.2[¶]()

* Security cleanups.

## 3.11.1[¶]()

* \[[JB-1272](https://juiceanalytics.atlassian.net/browse/JB-1272)\] **Fix** Improve snapshot and download image consistency.
* \[[JB-1349](https://juiceanalytics.atlassian.net/browse/JB-1349)\] **Fix** If a client admin has only one app redirect the management page to the management page for that one app.
* \[[JB-1387](https://juiceanalytics.atlassian.net/browse/JB-1387)\] **Fix** Add an id to the trend simple flavor.

## 3.11.0[¶]()

### Features in 3.11.0[¶]()

* \[[JB-1361](https://juiceanalytics.atlassian.net/browse/JB-1361)\] Snapshot migrations command \(migrate\_snapshots\)

### Improvements in 3.11.0[¶]()

* \[[JB-1377](https://juiceanalytics.atlassian.net/browse/JB-1377)\] Update date renderer to handle `recipe` library ingredients.
* \[[JB-1321](https://juiceanalytics.atlassian.net/browse/JB-1321)\] Extend the users api to get a list of users for an app.
* \[[JB-1319](https://juiceanalytics.atlassian.net/browse/JB-1319)\] Extend the invitations api to get a list of invitations for an app.
* \[[JB-1349](https://juiceanalytics.atlassian.net/browse/JB-1349)\] Allow client admins to invite users to an application.

### Fixes in 3.11.0[¶]()

* \[[JB-1389](https://juiceanalytics.atlassian.net/browse/JB-1389)\] More fixes to date renderer to handle `recipe` library ingredients.
* \[[JB-1357](https://juiceanalytics.atlassian.net/browse/JB-1357)\] Anonymizer will ignore falsey values

## 3.10.3[¶]()

* \[[JB-1352](https://juiceanalytics.atlassian.net/browse/JB-1352)\] **Fix** In the Ranked list slices, include the value of the metric in benchmark tooltips so the user has some way to see it when the benchmark and metric values overlap.

## 3.10.2[¶]()

* \[[JB-1374](https://juiceanalytics.atlassian.net/browse/JB-1374)\] **Fix** The period picker widget automatically shows up in Internet Explorer and then persists even after closing the global filters sidebar.
* \[[JB-1358](https://juiceanalytics.atlassian.net/browse/JB-1358)\] **Fix** In JB v3 apps, the list of tours for a stack would not show up when switched to that stack.

## 3.10.1[¶]()

* \[[JB-1359](https://juiceanalytics.atlassian.net/browse/JB-1359)\] **Fix** Removes dependency on s3 health check passing for servers

## 3.10.0[¶]()

### Features in 3.10.0[¶]()

* \[[JB-1337](https://juiceanalytics.atlassian.net/browse/JB-1337)\] Add metadata fields to App and FruitionClient to store extra custom data needed by implementations. This data can be changed at runtime in the Django admin.

### Improvements in 3.10.0[¶]()

* \[[JB-1296](https://juiceanalytics.atlassian.net/browse/JB-1296)\] Improved the discussion threads to scale nicely to smaller screen sizes.
* \[[JB-1309](https://juiceanalytics.atlassian.net/browse/JB-1309)\] For slices that have scrollbars, their scrollbars are not displayed in snapshot images.

## 3.9.2[¶]()

* \[[JB-1353](https://juiceanalytics.atlassian.net/browse/JB-1344)\] Change how manage users page provides csrf tokens to requests.

## 3.9.1[¶]()

* \[[JB-1344](https://juiceanalytics.atlassian.net/browse/JB-1344)\] Add missing map renderer to render factory. Add label to map renderer. JB3 apps weren’t able to render a map without these.
* \[[JB-1346](https://juiceanalytics.atlassian.net/browse/JB-1346)\] **Fix** The goals drawer in the Lollipop slice was not able to call the endpoint to save the goals.
* \[[JB-1317](https://juiceanalytics.atlassian.net/browse/JB-1317)\] **Fix** The “Select All” button was showing up in the global filters sidebar for an individual filter configured to only allow one item to be selected.
* \[[JB-1342](https://juiceanalytics.atlassian.net/browse/JB-1342)\] **Fix** Global filter items would not end up in the right sort order upon auto-refresh.

## 3.9.0[¶]()

### Features in 3.9.0[¶]()

* \[[JB-1302](https://juiceanalytics.atlassian.net/browse/JB-1302)\] Add app admins with read-only access to app-level usage reporting.

### Improvements in 3.9.0[¶]()

* \[[JB-1268](https://juiceanalytics.atlassian.net/browse/JB-1268)\] Introduced a new `$theme-header-style-dark` config in `theme.yaml` so that stack headers that are given darker backgrounds can get beautifully readable text.
* \[[JB-1292](https://juiceanalytics.atlassian.net/browse/JB-1292)\] Added ability to pass slice selections in the stack switcher. As well as collapse slices or select any response set in the stack switcher.
* \[[JB-1339](https://juiceanalytics.atlassian.net/browse/JB-1339)\] Added ability to pass a custom cache key to the anonymizers

## 3.8.1[¶]()

Note

This is an upcoming bugfix release.

* \[[JB-1303](https://juiceanalytics.atlassian.net/browse/JB-1303)\] **Fix** When a global filter is using a widget, its selection is not being passed correctly through the stack switcher.
* \[[JB-1313](https://juiceanalytics.atlassian.net/browse/JB-1313)\] **Fix** In the Details Table slice, when an item’s value is encapsulated in an object \(i.e `{value: null, class:'good'}`\) and is `null`, they don’t get sorted correctly.
* \[[JB-1289](https://juiceanalytics.atlassian.net/browse/JB-1289)\] **Fix** Selection pill for the Trend slice should show “&lt;min\_selected\_value&gt; to &lt;max\_selected\_value&gt;” instead of “&lt;num&gt; items”.

## 3.8.0[¶]()

### Features in 3.8.0[¶]()

* \[[JB-1268](https://juiceanalytics.atlassian.net/browse/JB-1268)\] Added `$theme-page-header-style` theme config with options “light” or “dark”. Default is “light”. Apps with dark background headers should be set to ‘dark’.

### Improvements in 3.8.0[¶]()

* \[[JB-502](https://juiceanalytics.atlassian.net/browse/JB-502)\] Relocate the ‘Forgot your password’ link so it is easier to find for the forgetful among us.
* \[[OPS-628](https://juiceanalytics.atlassian.net/browse/OPS-628)\] Have Jenkins decide which Dockerfiles to build and build them
* \[[JB-1266](https://juiceanalytics.atlassian.net/browse/JB-1266)\] Allows the leaderboard slice to return a max of 5 search results.
* \[[JB-1297](https://juiceanalytics.atlassian.net/browse/JB-1297)\] \(Internal core improvement\) Allow slices to pass extra data to the template that displays the text in the filter pill.
* \[[JB-1267](https://juiceanalytics.atlassian.net/browse/JB-1267)\] Don’t remove apps from an resent invitation. Use the client api to update apps on the manage users page instead of django forms.
* \[[JB-1301](https://juiceanalytics.atlassian.net/browse/JB-1301)\] Core fix to stop table locks in green threads

## 3.7.2[¶]()

* \[[JB-1295](https://juiceanalytics.atlassian.net/browse/JB-1295)\] **Fix** Slice alerts would always show up on screen widths below 768px.

## 3.7.1[¶]()

* \[[JB-1238](https://juiceanalytics.atlassian.net/browse/JB-1238)\] **Fix** Page title for help pages doesn’t show app label.
* \[[JB-1290](https://juiceanalytics.atlassian.net/browse/JB-1290)\] **Fix** Placement of the label `target` was not over the target range in the Trend slice for JB v3 apps.
* \[[JB-1285](https://juiceanalytics.atlassian.net/browse/JB-1285)\] **Fix** CardRenderer was returning an id that couldn’t be used for filtering.
* \[[JB-1288](https://juiceanalytics.atlassian.net/browse/JB-1288)\] **Fix** When performing a search in Ranked List v2, the list of items on the right side does not jump to the first found item while the slider on the left side does.
* \[[JB-1284](https://juiceanalytics.atlassian.net/browse/JB-1284)\] **Fix** The Lollipop slice legend was not including the `benchmark` and `goals` labels when the data had comparison/goal values, for JB v3 apps.
* \[[JB-1283](https://juiceanalytics.atlassian.net/browse/JB-1283)\] **Fix** The Lollipop slice mixin that links items to an url was not working in JB v3 apps.
* \[[JB-1298](https://juiceanalytics.atlassian.net/browse/JB-1298)\] **Fix** The global filters “PeriodPicker” widget would throw a Javascript error if it was supplied with no data.

## 3.7.0[¶]()

### Features in 3.7.0[¶]()

* \[[OPS-627](https://juiceanalytics.atlassian.net/browse/OPS-627)\] Production Ready Dockerfile

### Improvements in 3.7.0[¶]()

* \[[JB-1216](https://juiceanalytics.atlassian.net/browse/JB-1216)\] Enable prometheus for metrics logging. Metrics for recipe records and durations, cache hits, dataservices in progress and duration, and number of users per client are measured. `dataservices.servicebase.publish_metric` is deprecated and doesn’t do anything.
* \[[JB-701](https://juiceanalytics.atlassian.net/browse/JB-701)\] Default app.discusions\_group\_property is now “changeme” and help text is better
* \[[JB-1234](https://juiceanalytics.atlassian.net/browse/JB-1234)\] When there is an unread comment or a mention in a discussion thread, the discussion icon \(near the slice\) shows the avatar of the user that made the latest unread comment or mention.
* \[[JB-1245](https://juiceanalytics.atlassian.net/browse/JB-1245)\] Focus on the topic input field in the dropdown that allows the user to start a new discussion.
* \[[JB-1246](https://juiceanalytics.atlassian.net/browse/JB-1246)\] Now showing the user’s avatar with their name in the page header user drop down.
* \[[JB-1236](https://juiceanalytics.atlassian.net/browse/JB-1236)\] User mentions and avatars now show a tooltip on hover on the discussion view page. This tooltip shows the user’s name and sketching color. The logged in user can click on their name or avatar to go to their profile page.
* \[[JB-1247](https://juiceanalytics.atlassian.net/browse/JB-1247)\] Enable `@` mentions in the topic input field when starting a discussion.
* \[[JB-1248](https://juiceanalytics.atlassian.net/browse/JB-1248)\] Auto resizing of the comment input textarea on the discussion detail page so that it grows \(up to a max height\) and collapses as the user types.
* \[[JB-1233](https://juiceanalytics.atlassian.net/browse/JB-1233)\] Default profile avatars now have light grey backgrounds and are in the correct location to be collected into s3 buckets.
* \[[JB-1250](https://juiceanalytics.atlassian.net/browse/JB-1250)\] Removed the discussion thread from the discussion email notifications.
* \[[JB-1249](https://juiceanalytics.atlassian.net/browse/JB-1249)\] Include the `@handle` of the user in addition to the full name, when filtering `@` mention options in discussions.
* \[[JB-1240](https://juiceanalytics.atlassian.net/browse/JB-1240)\] Improved server health checks

## 3.6.1[¶]()

* **Fixed**: \[[JB-1262](https://juiceanalytics.atlassian.net/browse/JB-1262)\] Could not add a sketch to a discussion.
* **Fixed**: \[[JB-1261](https://juiceanalytics.atlassian.net/browse/JB-1261)\] Remove an old method of controlling what apps can see the HealthStream powerbar.
* **Improvement**: \[[JB-1243](https://juiceanalytics.atlassian.net/browse/JB-1243)\] UVA users get access to uvaqr app through SSO.

## 3.6.0[¶]()

### Features in 3.6.0[¶]()

* \[[JB-1228](https://juiceanalytics.atlassian.net/browse/JB-1228)\] Add experimental support for new recipe library. These recipes allow extra properties on Dimensions and Metrics, unify all shelves into a single shelf, support AutomaticShelf, can be extended by plugins. A sample application `recipedemo` shows how dataservices should be built.

### Improvements in 3.6.0[¶]()

* \[[JB-1232](https://juiceanalytics.atlassian.net/browse/JB-1232)\] The ‘Zoom Out’ button on the bubble slice is more noticeable and usable now. It jumps in to really let you know it’s there.
* \[[JB-1225](https://juiceanalytics.atlassian.net/browse/JB-1225)\] Change the client admin’s manage users page from a place where they could invite and manage app access but not see extra to a place where they can see extra but not invite and manage app access. Will we every have both? Sure, but for now API/Citrus is better for setting up user extras.
* \[[JB-1183](https://juiceanalytics.atlassian.net/browse/JB-1183)\] Remove our first user api. This isn’t used any more.
* \[[JB-1212](https://juiceanalytics.atlassian.net/browse/JB-1212)\] Add the date to the filename when someone downloads a snapshot of a slice.
* \[[JB-1122](https://juiceanalytics.atlassian.net/browse/JB-1122)\] For v3: Zooming while scrolling and panning is now disabled in the Bubble slice to allow for better user experience while scrolling the stack. The bubbles are also zoomed all the way out to fill available vertical space in their initial positions. The reset button has been renamed and given a better icon. For v2: zooming while scrolling and panning has been disabled.
* \[[JB-1222](https://juiceanalytics.atlassian.net/browse/JB-1222)\] If a data service is not provided, return an empty data response and add the WithNoData mixin. This makes creating a freeform slice that just displays a template easier to build.

### Fixes in 3.6.0[¶]()

* \[[JB-1223](https://juiceanalytics.atlassian.net/browse/JB-1223)\] Everyone should listen when the stack is in maintenance. This means global filters too.

## 3.5.2[¶]()

* \[[JB-1241](https://juiceanalytics.atlassian.net/browse/JB-1241)\] Fix UVA prod settings
* \[[JB-1244](https://juiceanalytics.atlassian.net/browse/JB-1244)\] Fix issue with anonymizing unicode values

## 3.5.1[¶]()

* \[[JB-1237](https://juiceanalytics.atlassian.net/browse/JB-1237)\] Fix EncryptedDimension when the value is null.
* \[[JB-1229](https://juiceanalytics.atlassian.net/browse/JB-1229)\] Set user’s first and last name correctly in UVA Single-signon.
* **Fixed**: \[[JB-1230](https://juiceanalytics.atlassian.net/browse/JB-1230)\] Option chooser core templates were being automatically applied to dropdown option choosers causing them to error.

## 3.5.0[¶]()

### Features in 3.5.0[¶]()

* \[[JB-1059](https://juiceanalytics.atlassian.net/browse/JB-1059)\] Added core templates for the Option Chooser slice that will be automatically used by the “buttons”, “metric” and “metric\_compare” renderer flavors if the slice hasn’t already been configured with a custom template.
* \[[JB-1158](https://juiceanalytics.atlassian.net/browse/JB-1158)\] Amazon Machine Images \(AMIs\) can now be built from any branch for any environment using an ENV argument and dynamic versioning.

### Improvements in 3.5.0[¶]()

* \[[JB-1184](https://juiceanalytics.atlassian.net/browse/JB-1184)\] Added a new config option to the keymetrics hierarchy slice that can turn off the grouping of the leaf nodes \(it is on by default\). Also updated the alignment of the node labels if the tree is oriented “left-to-right” or “right-to-left”.
* \[[JB-1218](https://juiceanalytics.atlassian.net/browse/JB-1218)\] For JBv3 apps, the option chooser dropdown will now default to showing the label of one selection in the button text. If more than 1 option is selected, it will say “\#num selected”.

### Fixes in 3.5.0[¶]()

* \[[JB-1219](https://juiceanalytics.atlassian.net/browse/JB-1219)\] Switching stacks after performing a search in the global filters was throwing a JS error and preventing any further searches from being performed.
* \[[JB-1220](https://juiceanalytics.atlassian.net/browse/JB-1220)\] A temporary ordering property was not deleted in a safe way.

## 3.4.3[¶]()

* **Fixed**: \[[JB-583](https://juiceanalytics.atlassian.net/browse/JB-583)\] Server error when a bad password reset link is loaded.
* **Fixed**: \[[JB-1217](https://juiceanalytics.atlassian.net/browse/JB-1217)\] Selections of slices that listen to themselves are now being passed through to it’s data service.
* **Fixed**: \[[JB-1211](https://juiceanalytics.atlassian.net/browse/JB-1211)\] Trying to show counts \(using the `showCount` flag\) in Ranked List v2 was throwing a JS error.

## 3.4.2[¶]()

* **Fixed**: \[[JB-1208](https://juiceanalytics.atlassian.net/browse/JB-1208)\] Minor code cleanups to maintain client branches.
* **Fixed**: \[[JB-1194](https://juiceanalytics.atlassian.net/browse/JB-1194)\] Don’t show frontend debug views to superusers in HIPAA environments

## 3.4.1[¶]()

* **Fixed**: \[[JB-1199](https://juiceanalytics.atlassian.net/browse/JB-1199)\] Migration issue with 3.3 -&gt; 3.4 upgrade

## 3.4.0[¶]()

### Features in 3.4.0[¶]()

* \[[JB-1175](https://juiceanalytics.atlassian.net/browse/JB-1175)\] Add a frontend debugging view for jb3 apps that shows SQL, automatic and custom filters. This is visible for superusers or by setting `recipe.render(show_debug=True)`.
* \[[JB-1069](https://juiceanalytics.atlassian.net/browse/JB-1069)\] Add pagination to slices and recipes. Setup the config with the pagination option for slices that have a lot of data that cause the page to get locked up. Make sure data services implement a `.order_by()` clause in their recipes.
* \[[JB-1098](https://juiceanalytics.atlassian.net/browse/JB-1098)\] Add a single signon settings for clients that can point to a Django view in `people.sso_views` that can authenticate a user based on request headers. This signon view can perform arbitrary logic so can be used for the HealthStream signon flow as well.

### Improvements in 3.4.0[¶]()

* \[[JB-1157](https://juiceanalytics.atlassian.net/browse/JB-1157)\] The stack navigation will now only appear on the page if the app has more than one stack.
* \[[JB-1162](https://juiceanalytics.atlassian.net/browse/JB-1162)\] Add search to the distribution slice. The matched items are highlighted.
* \[[JB-1167](https://juiceanalytics.atlassian.net/browse/JB-1167)\] Sort data in the distribution slice if it is not ordered by group. This prevents the same group from being created multiple times. Which is not what you want, believe me.
* \[[JB-735](https://juiceanalytics.atlassian.net/browse/JB-735)\] Don’t dismiss the Ranked List slider tooltip when a selection is made.

### Fixes in 3.4.0[¶]()

* \[[JB-1193](https://juiceanalytics.atlassian.net/browse/JB-1193)\] Add juicebox version number to app list in admin
* \[[JB-1033](https://juiceanalytics.atlassian.net/browse/JB-1033)\] Slices without slugs were using the wrong class name in themes.

## 3.3.2[¶]()

* **Fixed**: \[[JB-1182](https://juiceanalytics.atlassian.net/browse/JB-1182)\] In JB2 apps, formatting queries with unicode parameters was causing an exception.
* **Fixed**: \[[JB-1181](https://juiceanalytics.atlassian.net/browse/JB-1181)\] Themes were not updating when new slice types were added to an app. This caused the new slice to appear without any css styling.

## 3.3.1[¶]()

* **Fixed**: \[[JB-1177](https://juiceanalytics.atlassian.net/browse/JB-1177)\] User was not able to save a set of global filters if that stack hash had already been saved by another user.
* **Fixed**: \[[JB-1170](https://juiceanalytics.atlassian.net/browse/JB-1170)\] Unable to delete logo from JB3 apps.
* **Fixed**: \[[JB-1171](https://juiceanalytics.atlassian.net/browse/JB-1171)\] User was able to input invalid dates in the calendar widget of the global filters.
* **Fixed**: \[[JB-1180](https://juiceanalytics.atlassian.net/browse/JB-1180)\] Fixes missing superuser check in has\_object\_permissions for isClientAdmin check in the users api
* **Fixed**: \[[JB-1139](https://juiceanalytics.atlassian.net/browse/JB-1139)\] Catching Redis LockError and treating like a cache miss

## 3.3.0[¶]()

This release has nicer handling of collapsing and expanding slices and a cleanup of how slices track what is selected. The selection cleanup fixes issues we’ve been seeing where clearing the filter pill on a slice doesn’t always successfully clear a selection. It also lets us do some new things like build parallel ranked lists where your selection is maintained when you switch from list to list and paginate tables and card slices when there are 000s of items.

This release also changes how we manage user sessions. We can now set different session durations by client. The default session duration used to be 14 hours and it remained even if you closed your browser. The new default session duration is 14 days \(but this can be changed for each client\). Sessions expire when your browser closes or if the user has been inactive for the session duration amount of time. Users will receive a popup message when there approximately a half hour remaining on their session. If they move their mouse or perform any activity their session will be extended.

Lastly, have you ever wanted to clear the query cache for an app but didn’t necessarily want to clear the cache for \_all\_ apps? You can now do this via an API call. This will manifest itself in Citrus in the future, so that we can automatically clear an app’s cache when loading new data via an ETL job.

### Features in 3.3.0[¶]()

* \[[JB-1097](https://juiceanalytics.atlassian.net/browse/JB-1097)\] Don’t track selections in the slice responses anymore. To support pagination, selections cannot rely on the response since it won’t contain all the data.
* \[[JB-1123](https://juiceanalytics.atlassian.net/browse/JB-1123)\] Allow admins to clear the query cache for an app by calling `/api/v1/jb/apps/<APP_ID>/clear_cache/` with a `DELETE` request. You can get a list of apps at `/api/v1/apps/`.
* \[[JB-1069](https://juiceanalytics.atlassian.net/browse/JB-1069)\] Add pagination to slices and recipes. Setup the config with the pagination option for slices that have a lot of data that cause the page to get locked up. Make sure data services implement a `order_by` clause in their recipes.

### Improvements in 3.3.0[¶]()

* \[[JB-1160](https://juiceanalytics.atlassian.net/browse/JB-1160)\] Added a new base config option called `notifyOnDataSetChange` that will let a slice notify all the slices below it \(that are listening to it\) when it’s data set changes so they can fetch their data.
* \[[JB-1125](https://juiceanalytics.atlassian.net/browse/JB-1125)\] The `templateContext` is now passed to the content template in the Free Form slice when it has no data.
* \[[JB-983](https://juiceanalytics.atlassian.net/browse/JB-983)\] Updating Credstash, futures and cryptography
* \[[JB-877](https://juiceanalytics.atlassian.net/browse/JB-877)\] Enforces client specific session durations.
* \[[JB-1144](https://juiceanalytics.atlassian.net/browse/JB-1144)\] In slice titles, the emphasis text will by now be the default dark color \(black\), and the collapsable icon is truer to its functionality. This improvement reduces interaction confusion and increases readability of the slices.
* \[[JB-1141](https://juiceanalytics.atlassian.net/browse/JB-1141)\] Don’t show the entire list of labels in the tooltips of the global filter pills if there are too many. Too many being more than 10. Only show the first 10 labels then. And then say “+x more”.
* \[[JB-1143](https://juiceanalytics.atlassian.net/browse/JB-1143)\] Don’t force a white background on the slice header for non-collapsable slices. Instead make it inherit the slice’s background color so that the header looks fine on slices with transparent backgrounds.
* \[[JB-1137](https://juiceanalytics.atlassian.net/browse/JB-1137)\] The slice will now not have any UI elements that make it look collapsable when it’s configured as `collapsable:false`. Thus ending any confusion.
* \[[JB-1139](https://juiceanalytics.atlassian.net/browse/JB-1139)\] Catching LockError and treating like a cache miss

### Fixes in 3.3.0[¶]()

* \[[JB-1161](https://juiceanalytics.atlassian.net/browse/JB-1161)\] Stacks using the `OptionChooserWithDropdownViewMixin` mixin were not loading in IE and other browsers where ES6 constructs are not supported.

## 3.2.6[¶]()

Note

This is an upcoming bugfix release.

Add any release notes for 3.2.6 here.

## 3.2.5[¶]()

* **Fixed**: \[[JB-1151](https://juiceanalytics.atlassian.net/browse/JB-1151)\] Clearing the selections in the Lollipop Slice from the header would revert to the previous selection if any.
* **Fixed**: \[[JB-1153](https://juiceanalytics.atlassian.net/browse/JB-1153)\] The card slice was not rendering itself when it had no data even when it was setup with the `WithNoData` mixin. This was causing the action drawer to not render correctly.
* **Fixed**: \[[JB-1154](https://juiceanalytics.atlassian.net/browse/JB-1154)\] The `CardActionPlannerViewMixin` should trigger a forced FILTER\_CHANGE event on the successful saving of an action, so that the card slice that uses it \(and the slices below it\) are forced to re-fetch themselves from the server.
* **Fixed**: \[[JB-1152](https://juiceanalytics.atlassian.net/browse/JB-1152)\] Page title is now updated when dynamically switching stacks.

## 3.2.4[¶]()

* **Fixed**: \[[JB-1148](https://juiceanalytics.atlassian.net/browse/JB-1148)\] Right border of selected lollipop was not highlighting.
* **Fixed**: \[[JB-1142](https://juiceanalytics.atlassian.net/browse/JB-1142)\] When setting `minSelections:1` in the config for the Lollipop slice, it will now not be possible to deselect everything.
* **Fixed**: \[[JB-1130](https://juiceanalytics.atlassian.net/browse/JB-1130)\] Could not consistently switch to the same stack with a different hash. Now you can do so, consistently.
* **Fixed**: \[[JB-1134](https://juiceanalytics.atlassian.net/browse/JB-1134)\] The `CardActionPlannerViewMixin` mixin to work for JB v3. The v3 mixin was using code that belonged to v2.
* **Improvement**: \[[JB-1131](https://juiceanalytics.atlassian.net/browse/JB-1131)\] Adds a `has_counts` option to the ranked list `value_scale` renderer.

## 3.2.3[¶]()

* **Fixed**: \[[JB-1133](https://juiceanalytics.atlassian.net/browse/JB-1133)\] The default template that renders the count in the Ranked List slice would error if a blank string was setup as the format for the count in the metadata.
* **Fixed**: \[[JB-1128](https://juiceanalytics.atlassian.net/browse/JB-1128)\] Backported jb3’s improved .s formatter to jb2
* **Fixed**: \[[JB-1121](https://juiceanalytics.atlassian.net/browse/JB-1121)\] System tooltips now show up for the labels in the Leaderboard slice.
* **Fixed**: \[[JB-1127](https://juiceanalytics.atlassian.net/browse/JB-1127)\] The Map slice could show giant bubbles when the scale was not set.
* **Fixed**: \[[JB-1124](https://juiceanalytics.atlassian.net/browse/JB-1124)\] Stacks that were using the `ColorDataMixin` would not load in browsers that did not support the `let` ES6 construct. The `let` construct was changed to `var` and they load now.

## 3.2.2[¶]()

* **Fixed**: \[[JB-1115](https://juiceanalytics.atlassian.net/browse/JB-1115)\] The Trend slice was broken on touch devices.
* **Fixed**: \[[JB-1114](https://juiceanalytics.atlassian.net/browse/JB-1114)\] When making a selection in a slice, only the next slice was showing the filtering status. Now they all show it again.

## 3.2.1[¶]()

Big news here is a new slice config option. You can add `collapsable: false` in stack.yaml to prevent a slice from collapsing even if there’s no data. This issue bites us quite often.

We also added features to allow leaderboard colors to be carried to other slices, limit selectability in Bubble. Added an option for making self-refreshing global filter recipes easier to write. Now you can do the following to ensure a recipe doesn’t filter by the current dimension.

```text
# How to do a self-refreshing global filter the easy way
for dim in self.automatic_filter_keys:
    self.response['responses'].append(
      self.recipe().dimensions(dim).exclude_automatic_filter_keys(dim))


# The old way was this
for dim in self.automatic_filter_keys:
    # make a list of all automatic filters except for the current one
    everyone_but_me = [d for d in self.automatic_filter_keys if d != dim]
    self.response['responses'].append(
      self.recipe().dimensions(dim).limit_automatic_filters_to(dim))
```

On the fix side, there are lots of JB3 renderer fixes have been uncovered as we start using JB3 on more and more apps. Fixes to Option chooser, Distribution, Table, Leaderboard. Other fixes to switching between data sets and global filters. We also handle unicode better in our recipes and logging.

* **Added**: \[[JB-1083](https://juiceanalytics.atlassian.net/browse/JB-1083)\] Slices now support syncing colors between slices via the new `ColorDataMixin` config option.
* **Added**: \[[JB-891](https://juiceanalytics.atlassian.net/browse/JB-891)\] Slice collapsability is now configurable via the `collapsable` boolean. It’s enabled by default.
* **Improved**: \[[JB-1089](https://juiceanalytics.atlassian.net/browse/JB-1089)\] The Trend chart legend template now supports up to four series, a benchmark and a line.
* **Improved**: \[[JB-1066](https://juiceanalytics.atlassian.net/browse/JB-1066)\] The Bubble slice now supports the `minSelections` and `maxSelections` config options.
* **Fixed**: \[[JB-1111](https://juiceanalytics.atlassian.net/browse/JB-1111)\] The Option Chooser renderer wasn’t properly labeling multiple groups. Every flavor now ensures there is top-level name.
* **Fixed**: \[[JB-1105](https://juiceanalytics.atlassian.net/browse/JB-1105)\] Global filters weren’t working when an empty list was passed to `limit_global_filters_to`. Extended Recipe class with `exclude_automatic_filter_keys()` to provide a cleaner way to support refreshing global filters, and `include_automatic_filter_keys()` as a synonym for `limit_global_filters_to()`.
* **Fixed**: \[[JB-1062](https://juiceanalytics.atlassian.net/browse/JB-1062)\] The Table renderer wasn’t properly handling IdValueDimension. It now uses the `_id` property of the first dimension as the id and uses the `value` of the first dimension as the label.
* **Improved**: \[[JB-1106](https://juiceanalytics.atlassian.net/browse/JB-1106)\] The bars flavor of the Distribution renderer now supports ordered buckets via the `order` and `show_all` options.
* **Fixed**: \[[JB-1108](https://juiceanalytics.atlassian.net/browse/JB-1108)\] The JB3 Leaderboard renderer wasn’t properly setting row ids, which broke filtering.
* **Fixed**: \[[JB-1104](https://juiceanalytics.atlassian.net/browse/JB-1104)\] Re-added the initial loading overlay for v2 apps
* **Fixed**: \[[JB-1093](https://juiceanalytics.atlassian.net/browse/JB-1093)\] Switching between data sets in a slice didn’t respect the `minSelections` config, so items weren’t getting properly selected when switching to the second data set
* **Fixed**: \[[JB-1103](https://juiceanalytics.atlassian.net/browse/JB-1103)\] The Sentry Javascript client was configured to whitelist our old domain fruitiondata.com
* **Fixed**: \[[JB-1102](https://juiceanalytics.atlassian.net/browse/JB-1102)\] New data services logging didn’t properly handle unicode

## 3.2.0[¶]()

### Deprecations in 3.2.0[¶]()

* \[[JB-1046](https://juiceanalytics.atlassian.net/browse/JB-1046)\] JB3 dataservices no longer support juicebox1-style user filtering. Removed useless deprecation warnings on JB3.
* \[[JB-1017](https://juiceanalytics.atlassian.net/browse/JB-1017)\] The Trend slice deprecated the `dataSets` config option in favor of `series`. This will be removed in JB4.
* \[[JB-1016](https://juiceanalytics.atlassian.net/browse/JB-1016)\] The Ranked List v2 slice deprecated the `showcount` config option in favor of `itemTemplate`. This will be removed in JB4.

### Features in 3.2.0[¶]()

* \[[JB-378](https://juiceanalytics.atlassian.net/browse/JB-378)\] Stack startup time has been improved by fetching global filters in parallel with slices. The loading overlay has also been removed.
* \[[JB-950](https://juiceanalytics.atlassian.net/browse/JB-950)\] Stacks now load dynamically. Instead of forcing a full refresh every time you switch stacks, all the app stack data is available upfront and can be carried from stack-to-stack. Adds a new render flavor for the Freeform Slice called `switch_stacks`, as well as a new widget called `action-widget` that allows buttons in templates to switch stacks.
* \[[JB-999](https://juiceanalytics.atlassian.net/browse/JB-999)\] The Redshift connection base now provides a `DATABASE_REGISTY` setting to allow RecipePool and RecipeServiceBaseV3 to target different Redshift databases. We currently support `juicebox` and `healthstream` options.
* \[[JB-1057](https://juiceanalytics.atlassian.net/browse/JB-1057)\] The Custom slice now supports tree data structures in addition to lists.
* \[[JB-1020](https://juiceanalytics.atlassian.net/browse/JB-1020)\] The Flower slice now supports a `zoom` config option that can disable the default zooming behavior.
* \[[JB-763](https://juiceanalytics.atlassian.net/browse/JB-763)\] The Distribution slice didn’t handle thousands of items well since every item was a cell. Cells can now scale to represent groups of items, with an aggregated count at the top of the bin. Adds the `scaleCellSize` boolean and the `countField` option to specify which field to use for the count aggregation.

### Improvements in 3.2.0[¶]()

* \[[JB-1066](https://juiceanalytics.atlassian.net/browse/JB-1066)\] The Bubble slice now supports `minSelections` and `maxSelections` config options.
* \[[JB-1055](https://juiceanalytics.atlassian.net/browse/JB-1055)\] The frontend now uses native Javascript Promises and properly catches slice errors. Removes usage of `when.js` library.
* \[[OPS-266](https://juiceanalytics.atlassian.net/browse/OPS-266)\] The Vagrant environment has been upgraded from Ubuntu 14.04 to Ubuntu 16.04, and the config management has been updated and improved to match what we actually run in production. We’ve also added Packer pipelines to build AMIs for our new environments.
* \[[JB-1058](https://juiceanalytics.atlassian.net/browse/JB-1058)\] The Javascript client for Sentry has been upgraded to 3.9.1.
* \[[JB-836](https://juiceanalytics.atlassian.net/browse/JB-836), [JB-1068](https://juiceanalytics.atlassian.net/browse/JB-1068), [JB-1072](https://juiceanalytics.atlassian.net/browse/JB-1072)\] The Bubble slice has had a number of visual improvements, including better handling of the reset button, fixed color ranges and legends, better zooming, and more complimentary coloring for text. It also now properly applies formatters to the color values in the legend.
* \[[JB-1047](https://juiceanalytics.atlassian.net/browse/JB-1047)\] Data services logging has been vastly expanded with a dedicated log file for data service calls, as well as additional context added to events in Sentry. This adds information on query performance, parameters, and recipes, as well as support for using `self.log()` in data services. This also upgrades the Python client for Sentry to 5.32.0.
* The Users APIs now exposes `is_staff`, `is_superuser`, and `clientadmin_of` for the user detail endpoint.
* \[[JB-1038](https://juiceanalytics.atlassian.net/browse/JB-1038)\] BadRecipe exception messages now contain details about the ingredients used in a recipe and the columns they are sourced from.
* \[[JB-1028](https://juiceanalytics.atlassian.net/browse/JB-1028)\] Documentation has been updated with information and animations of available slices.
* \[[JB-1021](https://juiceanalytics.atlassian.net/browse/JB-1021)\] The readability of labels in the Flower slice has been improved
* \[[JB-1012](https://juiceanalytics.atlassian.net/browse/JB-1012)\] The Trend slice tooltip has been redesigned so it avoids overlapping the chart’s Y label.
* \[[JB-1025](https://juiceanalytics.atlassian.net/browse/JB-1025)\] The discussion button is now disabled while loading or filtering.
* \[[JB-981](https://juiceanalytics.atlassian.net/browse/JB-981)\] The Lollipop slice now updates stick and group visibility every time the data updates.
* \[[JB-1013](https://juiceanalytics.atlassian.net/browse/JB-1013)\] The frontend now includes the current slice’s selected data set name in `_selectedResponses` in a stack’s state.
* \[[JB-1004](https://juiceanalytics.atlassian.net/browse/JB-1004)\] The frontend no longer tries to fetch hash data if its the same as the hash currently embedded in the page.

### Fixes in 3.2.0[¶]()

* \[[JB-969](https://juiceanalytics.atlassian.net/browse/JB-969)\] Recipes now properly handle blend joins when blending to an existing join.
* RecipePool sometimes had instances of non-async queries unexpectedly go into async mode and blow up. \[[PR756](https://github.com/juiceinc/fruition/pull/756)\]
* \[[JB-1009](https://juiceanalytics.atlassian.net/browse/JB-1009)\] RecipePool caching was locking in some cases. The locks now expire after 100 seconds.
* \[[JB-1010](https://juiceanalytics.atlassian.net/browse/JB-1010)\] If a stack had multiple Sankey, Lollipop, or Ranked List slices the initial tooltip wouldn’t show up on the second slice.

## 3.1.13[¶]()

* **Fixed**: \[[JB-1101](https://juiceanalytics.atlassian.net/browse/JB-1101)\] Self-refreshing global filters that weren’t rendered with SlickGrid weren’t updating themselves properly.

## 3.1.12[¶]()

* **Fixed**: \[[JB-1087](https://juiceanalytics.atlassian.net/browse/JB-1087)\] Labels for the selected petal in the Flower slice were disappearing on mouseover if the same label didn’t exist in another flower that was moused over.
* **Improved**: The Users API now exposes the `is_staff` and `is_superuser` fields for the user detail endpoint. \[[PR741](https://github.com/juiceinc/fruition/pull/741)\]

## 3.1.11[¶]()

* **Fixed**: \[[JB-1085](https://juiceanalytics.atlassian.net/browse/JB-1085)\] The anonymizer wasn’t working for the download-data command.

## 3.1.10[¶]()

* **Improved**: \[[JB-1095](https://juiceanalytics.atlassian.net/browse/JB-1095)\] The Users API now exposes what clients a user is an admin for via a new `clientadmin_of` array.

## 3.1.9[¶]()

* **Fixed**: \[[JB-1080](https://juiceanalytics.atlassian.net/browse/JB-1080)\] The 3.1.8 fix for global filter anonymizing had a typo

## 3.1.8[¶]()

* **Fixed**: \[[JB-1077](https://juiceanalytics.atlassian.net/browse/JB-1077)\] Anonymizers for global filters weren’t enabled for demo users
* **Fixed**: \[[JB-1074](https://juiceanalytics.atlassian.net/browse/JB-1074)\] Hashr was throwing an exception when users would sometimes end up with more than one hash

## 3.1.7[¶]()

* **Fixed**: \[[JB-1073](https://juiceanalytics.atlassian.net/browse/JB-1073)\] The Ranked List v2 header didn’t support values with HTML text.
* **Fixed**: \[[JB-1071](https://juiceanalytics.atlassian.net/browse/JB-1071)\] The Option Chooser slice wasn’t clearing selections when the data service returned `selected=false`

## 3.1.6[¶]()

* **Fixed**: \[[JB-1061](https://juiceanalytics.atlassian.net/browse/JB-1061)\] The Vega slice wasn’t loading in IE9 and IE10
* **Fixed**: \[[JB-1060](https://juiceanalytics.atlassian.net/browse/JB-1060)\] JB3 apps weren’t loading in IE9
* **Fixed**: \[[JB-1042](https://juiceanalytics.atlassian.net/browse/JB-1042)\] Ranked List v2 and Lollipop weren’t rendering properly when the slice was collapsed. These slices now delay rendering until the slice is expanded.

## 3.1.5[¶]()

* **Fixed**: \[[JB-1056](https://juiceanalytics.atlassian.net/browse/JB-1056)\] A JavaScript error was causing slices not to resume fetching data after a failure
* **Fixed**: \[[JB-1053](https://juiceanalytics.atlassian.net/browse/JB-1053)\] Search was not working in the Ranked List v2 slice
* **Fixed**: \[[JB-1052](https://juiceanalytics.atlassian.net/browse/JB-1052)\] New items weren’t getting added properly when using self-refreshing global filters
* **Fixed**: \[[JB-1040](https://juiceanalytics.atlassian.net/browse/JB-1040)\] Renderers weren’t setting metadata properly when there was no data

## 3.1.4[¶]()

* **Fixed**: \[[JB-1034](https://juiceanalytics.atlassian.net/browse/JB-1034)\] Fix bucket number formatting for Distribution slice
* **Fixed**: \[[JB-1036](https://juiceanalytics.atlassian.net/browse/JB-1036)\] Option chooser dropdowns weren’t filtering in JB3
* **Fixed**: \[[JB-1031](https://juiceanalytics.atlassian.net/browse/JB-1031)\] Anonymizers are now enabled automatically for demo users in JB3

## 3.1.3[¶]()

* **Fixed**: \[[JB-1022](https://juiceanalytics.atlassian.net/browse/JB-1022)\] Cumulative Trend Renderer Issue when min date in series comes after the fiscal start
* **Fixed**: \[[JB-1023](https://juiceanalytics.atlassian.net/browse/JB-1023)\] Allow access to healthstream redshift in juicebox dev environment

This document will track upgrade notes between versions.

## Upgrading 3.12[¶]()

3.12 requires upgrading node to the current LTS version. Upgrade npm to the latest version as well.

> $ sudo npm cache clean -f $ sudo npm install -g n $ sudo n 6.11.3 $ sudo npm install [npm@latest](mailto:npm%40latest) -g \# Confirm the versions $ node –version v6.11.3 $ npm –version 5.5.1

Upgrade node before code has been deployed. Once code has been deployed, update npm packages for juicebox by changing to the src directory and installing.

> $ sudo su && su fruition $ cd /srv/services/fruition/src $ npm install \# Webpack files \# Activate the virtual environment $ source /srv/services/fruition/env/activate \# Set an appropriate settings file \(dev/staging or prod\) $ export DJANGO\_SETTINGS\_MODULE=fruition.settings.staging $ make all

## Vagrant Environment[¶]()

The local development environment has changed for 3.2.

If you already have the repo cloned, you’ll need to initialize and update the new Git submodules:

```text
$ git submodule init
$ git submodule update --recursive
```

This will update your `salt/formulas/juicebox-formula` directory to contain the new Salt formula for installing and configuring Juicebox.

We’ve upgraded our environment from Ubuntu 14.04 to Ubuntu 16.04, their newest LTS release. This requires a full destroy and recreate of the Vagrant environment:

```text
$ vagrant destroy -f
$ vagrant up
```

Expect the `vagrant up` command to take about 30 minutes.

## Server-side Operations[¶]()

* Python requirements have been updated.
* Hashr has a database migration that adds a new model for tracking user hash history.
* Due to the dynamic way the frontend now loads stacks, all apps have to be reloaded to avoid naming conflicts between stack templates.
* To support dynamic loading of the stacks, template names now get automatically prefixed with the stack slug \(if they aren’t already\). Any template names set in the config \(either through stack.yaml or by the data service\) will need to be updated.

