# Script Mikrotik on connect disconnect
Scripts para quando um usuário pppoe se conectar ou desconectar



## Instalação

1. Adicione os scripts ao Mikrotik através do comando `/system script add`:
```
/system script add name=pppoe-connect owner=SEU_USER policy=ftp,reboot,read,write,policy,test,password,sniff,sensitive,romon source=[SCRIPT_FONTE]

/system script add name=pppoe-disconnect owner=SEU_USER policy=ftp,reboot,read,write,policy,test,password,sniff,sensitive,romon source=[SCRIPT_FONTE]
```
2. Adicione no profile de seu servidor pppoe (Winbox = PPP -> Profile), por exemplo:
```
/ppp profile add comment="PPPoE Server" name=pppoe-server on-down=pppoe-disconnect on-up=pppoe-connect
```

# Equipe BrLink.org
