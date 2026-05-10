

C:\>powercfg
Invalid Parameters -- try "/?" for help

C:\>powercfg.exe /?

POWERCFG /COMMAND [ARGUMENTS]

Description:
  Enables users to control power settings on a local system.

  For detailed command and option information, run "POWERCFG /? <COMMAND>"

Command List:
  /LIST, /L          Lists all power schemes.

  /QUERY, /Q         Displays the contents of a power scheme.

  /CHANGE, /X        Modifies a setting value in the current power scheme.

  /CHANGENAME        Modifies the name and description of a power scheme.

  /DUPLICATESCHEME   Duplicates a power scheme.

  /DELETE, /D        Deletes a power scheme.

  /DELETESETTING     Deletes a power setting.

  /SETACTIVE, /S     Makes a power scheme active on the system.

  /GETACTIVESCHEME   Retrieves the currently active power scheme.

  /SETACVALUEINDEX   Sets the value associated with a power setting
                     while the system is powered by AC power.

  /SETDCVALUEINDEX   Sets the value associated with a power setting
                     while the system is powered by DC power.

  /IMPORT            Imports all power settings from a file.

  /EXPORT            Exports a power scheme to a file.

  /ALIASES           Displays all aliases and their corresponding GUIDs.

  /GETSECURITYDESCRIPTOR
                     Gets a security descriptor associated with a specified
                     power setting, power scheme, or action.

  /SETSECURITYDESCRIPTOR
                     Sets a security descriptor associated with a
                     power setting, power scheme, or action.

  /HIBERNATE, /H     Enables and disables the hibernate feature.

  /AVAILABLESLEEPSTATES, /A
                     Reports the sleep states available on the system.

  /DEVICEQUERY       Returns a list of devices that meet specified criteria.

  /DEVICEENABLEWAKE  Enables a device to wake the system from a sleep state.

  /DEVICEDISABLEWAKE Disables a device from waking the system from a sleep
                     state.

  /LASTWAKE          Reports information about what woke the system from the
                     last sleep transition.

  /WAKETIMERS        Enumerates active wake timers.

  /REQUESTS          Enumerates application and driver Power Requests.

  /REQUESTSOVERRIDE  Sets a Power Request override for a particular Process,
                     Service, or Driver.

  /ENERGY            Analyzes the system for common energy-efficiency and
                     battery life problems.

  /BATTERYREPORT     Generates a report of battery usage.

  /SLEEPSTUDY        Generates a diagnostic system power transition report.

  /SRUMUTIL          Dumps Energy Estimation data from System Resource Usage
                     Monitor (SRUM).

  /SYSTEMSLEEPDIAGNOSTICS
                     The system sleep diagnostics report has been deprecated and
                     replaced with the system power report. Please use the command
                     "powercfg /systempowerreport" instead.

  /SYSTEMPOWERREPORT Generates a diagnostic system power transition report.

  /POWERTHROTTLING   Control power throttling for an application.

  /PROVISIONINGXML, /PXML    Generate an XML file containing power setting overrides.



C:\>




```
C:\>powercfg.exe /query /?

POWERCFG /QUERY [<SCHEME_GUID> [<SUB_GUID>]]

Alias:
  POWERCFG /Q

Description:
  Displays the contents of the specified power scheme. If neither SCHEME_GUID
  or SUB_GUID are provided, the settings of the current active power scheme
  are displayed. If SUB_GUID is not specified, all settings in the specified
  power scheme are displayed.

Parameter List:
  <SCHEME_GUID>      Specifies a power scheme GUID. A power scheme GUID is
                     returned from the "POWERCFG /LIST" command.

  <SUB_GUID>         Specifies a power setting subgroup GUID. A power setting
                     subgroup GUID is returned from the "POWERCFG /QUERY"
                     command.

Examples:
  POWERCFG /QUERY

  POWERCFG /QUERY 381b4222-f694-41f0-9685-ff5bb260df2e
                  238c9fa8-0aad-41ed-83f4-97be242c8f20


C:\>powercfg.exe /batteryreport /?

POWERCFG /BATTERYREPORT [/OUTPUT <FILENAME>] [/XML] [/TRANSFORMXML <FILENAME.XML>]


Description:
  Generates a report of battery usage characteristics over the lifetime of the
  system. The BATTERYREPORT command will generate an HTML report file in the
  current path.

Parameter List:
  /OUTPUT <FILENAME>     Specify the path and filename to store the battery
                         report HTML or XML file.

  /XML                   Format the report file as XML.

  /DURATION <DAYS>       Specify the number of days to analyze for the report.

  /TRANSFORMXML <FILENAME.XML>   Reformat an XML report file as HTML.

Examples:
  POWERCFG /BATTERYREPORT
  POWERCFG /BATTERYREPORT /OUTPUT "batteryreport.html"
  POWERCFG /BATTERYREPORT /OUTPUT "batteryreport.xml" /XML
  POWERCFG /BATTERYREPORT /TRANSFORMXML "batteryreport.xml"
  POWERCFG /BATTERYREPORT /TRANSFORMXML "batteryreport.xml" /OUTPUT "batteryreport.html"


C:\>
```
