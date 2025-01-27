# Configuration

- [Configure PLC Connection](#configure-plc-connection)
  - [Configure Databus](#configure-databus)
  - [Configure S7 Connector](#configure-s7-connector)
- [Configure Data Service](#configure-data-service)
  - [Configure the adapter](#configure-the-adapter)
  - [Configure an asset with variables](#configure-an-asset-with-variables)
- [Configure Performance Insight](#configure-performance-insight)
    - [Configure a dashboard](#configure-a-dashboard)
    - [Configure widgets](#configure-widgets)
    - [Configure KPIs](#configure-KPIs)
		
# Configure PLC Connection

To read data from the PLC and provide the data, we will use S7 Connector to establish connection with the PLC via OPC UA.
The S7 Connector sends the data to the Databus, where the Data Service app can collect what is needed.
In order to build this infrastructure, these apps must be configured properly:

- Databus
- S7 Connector

## Configure Databus

In your IEM open the Databus and launch the configurator.

Add a user with this topic:
`"ie/#"`

<p align="center"><kbd><img src="graphics/IE_Databus_User.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/IE_Databus.PNG" /></kbd></p>

Deploy the configuration.

## Configure S7 Connector

In your IEM open the S7 Connector and launch the configurator.

Add a data source:

<p align="center"><kbd><img src="graphics/S7_Connector_Data_Source.PNG" /></kbd></p>

Add needed tags:

<p align="center"><kbd><img src="graphics/S7_Connector_Configuration.PNG" /></kbd></p>

Edit the settings:

<p align="center"><kbd><img src="graphics/S7_Connector_Settings.PNG" /></kbd></p>

Hint: Username and password should be the same for all system apps, e.g. "edge" / "edge".

Deploy and start the project.

# Configure Data Service

In your IED Web UI open the app Data Service.

Hint: If an error screen appears saying "...unauthorized...", please restart the Data Service app, wait a moment and try again to open it.

## Configure the adapter

On the left bar click the icon "Adapters" and choose the SIMATIC S7 Connector (MQTT).

Click the edit icon on the right to open the adapter configuration.

<p align="center"><kbd><img src="graphics/Data_Service_Adapter.PNG" /></kbd></p>

Add the missing entries for username and password (again "edge"/"edge") and save it.

<p align="center"><kbd><img src="graphics/Data_Service_Adapter_Config.PNG" /></kbd></p>

Hint: Sometimes the Data Service app must be restarted, to take over the adapter changes.

## Configure an asset with variables

On the left bar click the icon "Assets & Connectivity". For the "edge" asset you can add child assets as needed.

Choose "Create first variable" or "Add variable" on the right side to add tags.

The required tank application variables are: tank level, tank temperature, produced bottles and faulty bottles.

<p align="center"><kbd><img src="graphics/Data_Service_Assets.PNG" /></kbd></p>

<p align="center"><kbd><img src="graphics/Data_Service_Variable.PNG" /></kbd></p>

# Configure Performance Insight

In your IED Web UI open the app Performance Insight.

<p align="center"><kbd><img src="graphics/Performance_Insight_Icon.png" /></kbd></p>

Hint: When opening the application for the first time a lincese message might pop up (no relationship to IE Hub). Just accept the message and start using the application

## Configure a dashboard

On the main panel the dashboard overview will show the option to create a new dashboard (operating at the highest hirerchical level configured in data service)

<p align="center"><kbd><img src="graphics/Performance_Insight_Create_Dashboard.png" /></kbd></p>

Insert a dashboard name and select the time frame that should be display per default for all signals

<p align="center"><kbd><img src="graphics/Performance_Insight_Config_Dashboard.png" /></kbd></p>

## Configure widgets

When configuring a widget, Performance Insight offers the following types:

<p align="center"><kbd><img src="graphics/Performance_Insight_Widgets.png" /></kbd></p>

The standard widget configuration has to define some details

<p align="center"><kbd><img src="graphics/Performance_Insight_Define_Details.png" /></kbd></p>

The following steps are: select parameters and define display options 

<p align="center"><kbd><img src="graphics/Performance_Insight_Select_Parameter.png" /></kbd></p>

<p align="center"><kbd><img src="graphics/Performance_Insight_General_Display.png" /></kbd></p>

In case of a Gauge Widget an additional dialog will appear with the display boundaries parametrization

<p align="center"><kbd><img src="graphics/Performance_Insight_Gauge_Display.png" /></kbd></p>

The first widget is a gauge display for the actual production quality (with its respective warning and alarming levels)

<p align="center"><kbd><img src="graphics/Performance_Insight_Gauge_Widget.png" /></kbd></p>

Several widgets have been configured as single value display (with Min, Avg and Max Values)

<p align="center"><kbd><img src="graphics/Performance_Insight_Value_Widget.png" /></kbd></p>

Another configured widget is a diagram display for the actual tank level

<p align="center"><kbd><img src="graphics/Performance_Insight_Diagram_Widget.png" /></kbd></p>

The last used widget on this application example is a Gantt diagram. The first step is to configure a status mapping

<p align="center"><kbd><img src="graphics/performance-insight-gantt-status-mapping.png" /></kbd></p>

Afterwards the Widget has to be added. The Gantt Overview will be displayed on the dashboard

<p align="center"><kbd><img src="graphics/performance-insight-gantt-overview.png" /></kbd></p>

By clicking the detailed view icon, a detailed Gantt diagram will be shown (more visible data)

<p align="center"><kbd><img src="graphics/performance-insight-gantt-detail-view.png" /></kbd></p>

## Configure KPIs

Additional values (also named KPIs) can be calculated out of the existing variables.

In order to calculate the production quality a KPI type has been defined

<p align="center"><kbd><img src="graphics/Performance_Insight_KPI_Calculation.png" /></kbd></p>

This quality production KPI has been displayed using a gauge widget (frist widget mentioned). KPI has been instanced within a widget

<p align="center"><kbd><img src="graphics/Performance_Insight_KPI_Gauge_Widget.png" /></kbd></p>