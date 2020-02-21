## <a name="fiscal-calendar-period-to-msdyn_fiscalcalendarperiods"></a>Período do calendário fiscal para msdyn_fiscalcalendarperiods

Este modelo sincroniza dados entre aplicativos do Finance and Operations e do Common Data Service.

Campo do Finance and Operations | Tipo de mapa | Outro campo Dynamics 365 | Valor padrão
---|---|---|---
COMMENTS | = | msdyn_comments | 
ENDDATE | = | msdyn_enddate | 
MONTH | >< | msdyn_month | 
CALENDAR | = | msdyn_fiscalcalendar.msdyn_calendar | 
QUARTER | >< | msdyn_quarter | 
SHORTNAME | = | msdyn_shortname | 
STARTDATE | = | msdyn_startdate | 
TYPE | >< | msdyn_fiscalperiodtype | 
PERIODNAME | = | msdyn_periodname | 
FISCALYEAR | = | msdyn_fiscalcalendaryear.msdyn_name | 
CALENDAR | = | msdyn_fiscalcalendaryear.msdyn_fiscalcalendarname | 
