---
uid: Web_apps_Feature_Release_10.5.3
---

# DataMiner web apps Feature Release 10.5.3 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
>
> - For release notes related to the general DataMiner release, see [General Feature Release 10.5.3](xref:General_Feature_Release_10.5.3).
> - For release notes related to DataMiner Cube, see [DataMiner Cube Feature Release 10.5.3](xref:Cube_Feature_Release_10.5.3).

## Highlights

*No highlights have been selected yet.*

## New features

#### Dashboards/Low-Code Apps: Support for variables of type Boolean [ID 41845]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When editing a dashboard or a low-code app, you can now also create variables of type Boolean.

Also, boolean values can now be passed in the URL of a dashboard. See the following example of a query parameter:

`?data={"components": [{"cid":1, "select": {"booleans": ["true"]}}]}`

#### Dashboards/Low-Code Apps: Component themes now allow you to specify an accent color [ID 41859]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When customizing a component theme, you can now also specify an accent color.

By default, this accent color will be identical to the app color. For example, in the *Dashboards* app, the accent color will by default be green.

#### Dashboards/Low-Code Apps: New Toggle component [ID 41903] [ID 41911] [ID 41915]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When creating or updating a dashboard or a low-code app, you can now add *Toggle* components, which are visualized as switches.

When configuring a *Toggle* component, you can link it to a variable of type Boolean, set its default value, and specify a label and an icon. The font color, background color and accent color of the component will automatically be adapted to those specified in the theme of the dashboard or app.

When you add a *Toggle* component to a low-code app, you can also configure a *Set value* action for it. This action will allow users to either set the current value of the component in question to either a static value (True, False, or Empty) or link the component to a variable of type Boolean.

## Changes

### Enhancements

#### Low-Code Apps - Interactive Automation scripts: Redesigned UI components 'Calendar' and 'Time' [ID 41529]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

The UI components `UIBlockType.Calendar` and `UIBlockType.Time` have been redesigned.

Currently, by default, the existing components will still be used by default to keep the UI aligned. If you want to use the new *Button* component, then add the following argument to the URL of the low-code app:

`?useNewIASInputComponents=true`

#### Dashboards/Low-Code Apps: Node edge graph component now supports real-time updates [ID 41545]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

The *Node edge graph* component now supports real-time updates.

#### DataMiner Object Models: A confirmation box will now appear when you remove a section from a DOM form [ID 41792]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

Up to now, When you removed a section from a DOM instance form with multiple sections, that section would be removed immediately, without any notification. From now on, a confirmation box will appear, prompting the user to either confirm or cancel the action.

#### Dashboards/Low-Code Apps: Linking a Trigger component to a Query filter component now allows you to refetch the columns and column statistics [ID 41799]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

By linking a *Trigger* component to a *Query filter* component, it is now possible to have the columns and column statistics refetched.

#### DataMiner root page: Links to deprecated DataMiner XBAP and legacy Reports & Dashboards app have now been removed [ID 41844]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When, on the root page of a DataMiner Agent (i.e. `https://myDMA/root/tools`), you click the user icon and then select *Tools*, a *Tools* page will open.

Up to now, this page would still contain links to the XBAP version of DataMiner Cube and to the legacy *Reports & Dashboards* app. As both are now deprecated, the links to both those apps as well as the *Clean DataMiner Cube XBAP Cache* link have now been removed.

#### Dashboards/Low-Code Apps - Time range component: Automatic refresh now has to be implemented via a linked Trigger component [ID 41931]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

Up to now, when you wanted a *Time range* component to automatically refresh its data at regular intervals, you had to enable the *Allow refresh* option. This would then cause a refresh timer to appear (by default set to 10 seconds).

The *Allow refresh* option has now been removed. In order to have *Time range* component refresh its data at regular intervals, you now have to link a *Trigger* component to it as a filter.

#### Dashboards/Low-Code Apps - Time range component: Moved from the 'General' category to the 'Basic controls' category  [ID 41934]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

The *Time range* component has been moved from the *General* category to the *Basic controls* category. Also, its icon has now been updated to better represent a range.

#### GQI DxM: Web applications will now use the GQI DxM installed on the local DMA to build and run GQI queries [ID 41949] [ID 42010]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

From now on, the DataMiner web applications will by default use the GQI DxM installed on the local DataMiner Agent when building and running GQI queries.

#### Low-Code Apps: Default set of icon files will be created when you create a new low-code app [ID 42004]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When you create a new low-code app on the root page of a DataMiner Agent (e.g. `https://myDMA/root/`), from now on, a default set of icon files will automatically be created for that app.

#### Dashboards/Low-Code Apps - Node edge graph component: Zoom factor for arrows and KPI labels on edges is now capped [ID 42011]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

From now on, the zoom factor for arrows and KPI labels on edges will be capped. This means that, when you keep zooming in on a node edge graph, at some point, the magnification factor of the arrows and the KPI labels on edges will no longer change.

### Fixes

#### Dashboards/Low-Code Apps - Table component: Refetching data would cause the data in the table to shift across the different pages [ID 41638]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When a *Table* component refetched its data, in some cases, the data would incorrectly shift across the different pages.

#### Dashboards/Low-Code Apps - Timeline component: Problem with custom timezones [ID 41839]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When using a custom timezone, in some cases, that timezone would not be applied correctly in action configurations or when linking to certain components.

#### Dashboards/Low-Code Apps - State component: Scale of text would not be updated when the value of the linked parameter changed [ID 41843]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When a *State* component was linked to a parameter, and the size of that component was set to "Auto", up to now, the scale of the text would not be updated when the value of the parameter changed. In some cases, this would render the text unreadable.

#### Low-Code Apps - Timeline component: Post actions after 'Set viewport' or 'Highlight time range' actions would incorrectly not be executed [ID 41862]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When a post action was configured to get triggered after a *Set viewport* or a *Highlight time range* action, up to now, the post action would incorrectly not be executed.

#### Authentication screen would not redirect users to the correct app [ID 41900]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When you tried to log on to a DataMiner web app, in some cases, the authentication screen would not redirect you to the correct app.

#### Low-Code Apps: Problem when using queries in flows [ID 41955]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When a low-code app used queries in some of its flows, in some cases, it could become unresponsive.

#### Dashboards app: Users would not be allowed to see any of the alarms listed in an Alarm table component of a shared dashboard [ID 41965]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When users consulted a shared dashboard containing an *Alarm table* component on which an element filter or a view filter was applied, in some cases, they would incorrectly not be allowed to see any of the alarms listed in that *Alarm table* component.

#### Dashboards/Low-Code Apps - Grid component: Problem when a linked Trigger component is triggered while viewing the last page [ID 41991]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When a *Trigger* component linked to a *Grid* component was triggered while you were viewing the last page of grid data, a skeleton loading animation would incorrectly be shown. From now on, the last values will remain on the screen until the new data has been fetched.

#### Low-Code Apps: 'Change variable' action would not always apply the correct value when linked to dynamic data [ID 42027]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

In some cases, the *Change variable* action would not apply the correct value, especially when it was linked to dynamic data.

#### Monitoring app: Problem when consulting alarm details when using external authentication via SAML [ID 42037]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

When you logged in to the *Monitoring* app using external authentication via SAML, and then opened an alarm, the user name of the alarm owner would be incorrect.

#### Low-Code Apps: Not possible to execute a 'Change variable' action via the URL of the app [ID 42038]

<!-- MR 10.4.0 [CU12] - FR 10.5.3 -->

Up to now, it would incorrectly not be possible to execute a *Change variable* action via the URL of the app.
