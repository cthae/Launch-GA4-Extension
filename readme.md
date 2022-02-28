# GA4 extension for Launch

This extension is aimed to allow comfortable GA4 implementations via Adobe Launch.

## Progress

- Extension CFG: **90%**
 - Extension config allowing multiple GA4 measurement ids **Done**
 - Flexible validation and pre-population **Done**
 - Allow DE usage for Measurement IDs **Done**
 - Allow the ability for the user to choose where the lib is loaded **In Progress**  
 - Design **TBD**

- GA4 Config Data Element[^1] **80%**
 - Extension config allowing multiple properties **Done**
 - Flexible validation and pre-population **Done**
 - Allow DE usage for names and values **Done**
 - Add scope switch **Done**
 - A way to make these DEs available in Actions **On Hold**, 
 - Design **TBD**

- GA4 Event Action[^2] **5%**
 - Add a switch for Page View **Planned**
 - Add an option to override or add new dimensions in every action **Planned**
 - Validation **Planned**
 - Prepopulation **Planned**
 - Add the ability to hook in an EEC payload[^3] **On Hold**

- Deploy the gtag library action **0%**
 - Look at the conflicts with existing GA UA extensions **Planned**
 - Allow usage of already deployed gtag lib **On Hold**
 - Conflicts with already deployed trackers? **On Hold**

- Enhanced E-commerce[^4] **0%**
 - Extend the UI of the Event Action to allow for Manual setting of EEC fields **Planned**
 - Manual for EEC set up? **On Hold**


[^1]: The aim of the GA4 config DE is to replicate what GTM has always had for UA tags, but no longer has for GA4 tags. You're supposed to set a set of dimensions (properties and parameters) here and their scope, after which you'll be able to re-use these config DEs with event tracking actions.

[^2]: There's no real reason to split Events and Pageviews. From technical perspective, a Pageview is just an event named page_view in GA4. 

[^3]: It is important that events that carry EEC payloads with them would be able to carry certain custom dimensions with them so that the analysts then could seamlessly pull dimensions when looking at the EEC metrics, like transactions, refunds and whatnot. Therefore, EEC events should be implemented as your normal custom events. GTM follows this thing too.

[^4]: There are many ways to implement EEC: let the user select DEs for every field? Reimplement GTM's auto-DL parser? Auto-DL parser for UA EEC -> GA4 EEC or straight away GA4 EEC? The MVP for this would be probably just allowing the user to manually set all fields in the UI using DEs. And then we'll see. Reimplementing Google's DL parser shouldn't be an issue and mapping UA EEC to GA4 EEC is not a problem either, it'll just take time.