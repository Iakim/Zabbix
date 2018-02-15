# Zabbix-ScheduledTask

### Passo 1:
Copie o arquivo DiscoverScheduledTasks.ps1 para a pasta do Zabbix Agent
Normalmente a pasta padrão é "C:\Zabbix\"

### Passo 2: 
Altere se necessário a variável $path no arquivo DiscoverScheduledTasks.ps1, está setado o padrão "\"

### Passo 3:
No arquivo de configuração do Zabbix Agent adicione os seguintes parâmetros:

    EnableRemoteCommands=1

    UnsafeUserParameters=1
    
    Timeout=30

    UserParameter=TaskSchedulerMonitoring[*],powershell -NoProfile -ExecutionPolicy Bypass -File "C:\Zabbix\DiscoverScheduledTasks.ps1" "$1" "$2"

### Passo 4:
Reinicie o serviço do Zabbix Agent
     
     service zabbix-agent restart

### Passo 5: 
Vincule o template Template Windows Task Scheduled ao host.
     
# Telegram: @iakim
