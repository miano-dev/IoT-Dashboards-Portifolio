# IoT Dashboards Portfolio

### Connected Monitoring · Industrial IoT · Electric Vehicle (EV) Mobility

This portfolio presents two engineering projects focused on turning operational data into clear, useful dashboards. The projects cover sensor monitoring, telemetry, fleet visibility, battery information and secure service integration.

The repository provides public-facing project summaries and high-level architecture notes. The application source code and private implementation details remain in their respective private repositories.

---

## 1. Climate Data Monitoring & Reporting

**Domain:** Environmental monitoring · IoT sensor telemetry · Data reporting  
**Source repository:** Private implementation repository

### Overview

The Climate Data Monitoring & Reporting dashboard provides a web interface for viewing live environmental sensor readings and historical monitoring data. It brings together telemetry from connected sensors and presents the information through dashboard views, trends and configurable tabular reporting.

### Key capabilities

- **Environmental sensor telemetry:** Temperature, humidity, NPK measurements and other configured monitoring readings.
- **Historical monitoring:** Time-series data and historical graphs backed by InfluxDB.
- **Operational visibility:** Dashboard views for configured monitoring areas and their sensor readings.
- **Spreadsheet reporting:** An optional Google Sheets data source for separate tabular information, with configurable columns and chart axes.
- **Access-controlled configuration:** Public visitors can view dashboard information while authorised administrators manage data-source settings.

### High-level data architecture

```text
Connected Sensors
       |
       v
Sensor Telemetry
       |
       v
     InfluxDB
       |
       v
Dashboard Views
       |
       +----> Live Readings
       |
       +----> Historical Trends


Optional Google Sheets CSV
       |
       v
Separate Tabular Reporting
       |
       v
Configurable Tables and Charts
```

The sensor telemetry and spreadsheet reporting paths are kept separate. Spreadsheet records are not treated as sensor measurements.

### Engineering focus

- IoT data acquisition and telemetry visualisation
- Environmental and time-series monitoring
- Historical analysis and reporting
- Integration of multiple data sources
- Configurable dashboards and reporting
- Access control for administrative settings
- Clear separation between sensor data and general tabular records

---

## 2. EV Mobility Dashboard

**Domain:** Electric Vehicles (EV) · Fleet operations · Battery and telemetry monitoring  
**Source repository:** [EV_Mobility_Dashboard](https://github.com/miano-dev/EV_Mobility_Dashboard) · *Private*

### Overview

The EV Mobility Dashboard is an operations interface designed for electric-vehicle fleet visibility. It brings together vehicle location information, battery and power telemetry, payment verification and safety-status information in one operational view.

The dashboard is structured to connect with live services and present verified information to operators. It does not rely on fabricated vehicle identities, coordinates, battery readings, payment records or controller responses.

### Key capabilities

- **Fleet visibility:** Vehicle location and operational status.
- **Battery and power monitoring:** Battery readings, power values, cell information, temperature measurements and alerts.
- **Historical telemetry:** Time-series data ingestion and queries through a secured server-side connection.
- **Payment verification:** Safaricom M-Pesa payment callbacks, receipt deduplication, account allocation and reconciliation.
- **Safety-status awareness:** Visibility of safety states and controller responses, with safety-critical workflows dependent on verified system status and validated controller integration.

### High-level system architecture

```text
Electric Vehicles
       |
       v
Vehicle Telemetry
(Location, Battery, Power, Status)
       |
       v
Secure Backend Services
       |
       +--------------------+
       |                    |
       v                    v
Time-Series Data       Payment Services
       |                    |
       v                    v
Historical Data        Verified Transactions
       |                    |
       +---------+----------+
                 |
                 v
          EV Operations
             Dashboard
                 |
                 v
       Fleet Visibility,
       Alerts and Reporting
```

### Current integration approach

The dashboard is prepared for integration with live vehicle telemetry, payment services and controller systems. It starts with an empty data store so that operators are not presented with invented operational records.

Safety-critical workflows require the actual controller integration, verified system states and completed safety validation before they can be enabled.

### Technology and engineering areas

- React and TypeScript
- TanStack Start and TanStack Router
- Tailwind CSS
- Leaflet for location visualisation
- Vehicle telemetry and time-series data integration
- Safaricom M-Pesa payment verification
- Secure server-side API integration
- Battery, power and safety-status monitoring

---

## Portfolio Engineering Themes

Together, these projects demonstrate work across:

| Engineering area | Project application |
|---|---|
| Internet of Things (IoT) | Connected sensor monitoring and telemetry |
| Data visualisation | Live readings, historical trends and operational dashboards |
| Time-series systems | InfluxDB and historical telemetry workflows |
| Environmental monitoring | Temperature, humidity and other sensor measurements |
| Electrical and energy systems | Battery and power monitoring |
| Electric mobility | EV fleet visibility and operational information |
| Systems integration | Sensors, backend services, dashboards and payment workflows |
| Application security | Access-controlled settings and server-side integrations |
| Data integrity | Separation of data sources and verification of operational records |

## Source Code and Project Access

The two application repositories are private. This public portfolio documents their purpose, capabilities and high-level engineering architecture; it does not publish application source code, credentials, privileged configuration, private datasets or proprietary implementation files.

- **Climate Data Monitoring & Reporting** — private source repository.
- [EV_Mobility_Dashboard — private repository](https://github.com/miano-dev/EV_Mobility_Dashboard)

---

**John Muturi Miano**  
Instrumentation & Control Engineering · Industrial Automation · IoT · Embedded Systems

[GitHub Profile](https://github.com/miano-dev)
