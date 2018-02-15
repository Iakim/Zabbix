# Zabbix-ScheduledTask

### Passo 1:
Copie o arquivo DiscoverScheduledTasks.ps1 para a pasta do Zabbix Agent
Normalmente a pasta padr�o � "C:\Zabbix\"

### Passo 2: 
Altere se necess�rio a vari�vel $path no arquivo DiscoverScheduledTasks.ps1, est� setado o padr�o "\"

### Passo 3:
No arquivo de configura��o do Zabbix Agent adicione os seguintes par�metros:

    EnableRemoteCommands=1

    UnsafeUserParameters=1
    
    Timeout=30

    UserParameter=TaskSchedulerMonitoring[*],powershell -NoProfile -ExecutionPolicy Bypass -File "C:\Zabbix\DiscoverScheduledTasks.ps1" "$1" "$2"

### Passo 4:
Reinicie o servi�o do Zabbix Agent
     
     service zabbix-agent restart

### Passo 5: 
Vincule o template Template Windows Task Scheduled ao host.
     
# Telegram: @iakim
