Diferentemente da dica How-To :: extraindo isos de XBox360 no Linux com o Xipper (mas com o mesmo propósito), veremos agora como extrair pela linha de comando imagens ISO de XBox360 e para tal usaremos o programa extract-iso, o motor sob o capô do Xipper.

Então… e isso serve para todos:

```
$ wget http://ufpr.dl.sourceforge.net/project/extract-xiso/extract-xiso%20source/extract-xiso-2.7.1.tar.gz
$ tar xf extract-xiso-2.7.1.tar.gz 
$ cd extract-xiso/
$ make
$ sudo mv -v extract-xiso /usr/local/bin/
```

log:

+ expandir fonte

UTILIZANDO

Para extrair a imagem iso, usei a seguinte sintaxe:

```
$ extract-xiso -x -s -d $HOME/DEST_DIR/ /../caminho-da-imagem.iso
```

Ou seja: o programa seguido das opções -x (de extrair) -s (de pular o diretório $SystemUpdate) e -d (que especifica o diretório de destino) e o caminho da imagem.iso.

Você até pode remover a opção -s (de pular o diretório $SystemUpdate), mas dizem que pode acarretar em problemas em seu RGH desbloqueado.

O PULO DO GATO

Para facilitar crei um alias em seu ~/.bashrc com o seguinte conteúdo:

```
#--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--#
# Extrair ISOS de XBox360 para o formato GOD.
#
# Usando: create-god caminho-da-imagem.iso
#
# Exemplos via modo cli:
#
# Para pular o diretório $SystemUpdate: extract-xiso -x -s -d $HOME/DEST_DIR/ /../caminho-da-imagem.iso
# ou
# Para executar normalmente: extract-xiso -x -d $HOME/DEST_DIR/ /../caminho-da-imagem.iso
# 
# Alternativa gráfica: https://edpsblog.wordpress.com/2015/03/21/how-to-extraindo-isos-de-xbox360-no-linux-com-o-xipper/
#
#--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--=--#

alias create-god='cd && mkdir XBox360/GOD && extract-xiso -x -s -d $HOME/XBox360/GOD/'
```

Salve o arquivo, abra um novo terminal e digite:

```
$ create-god caminho-da-imagem.iso
```

Isso acarretará na criação das pastas XBox360/GOD/ em sua $HOME e a extração do conteúdo da iso na pasta GOD, como em /home/edps/XBox360/GOD/, daí bastará copiar o conteúdo desta pasta para um dispositívo de memória (pendrive,hd externo) e usar em seu XBox360 com RGH/JTAG.

* mas lembre-se de renomear a pasta GOD para o nome do jogo convertido após a extração da iso, pois se sempre mantiver o nome GOD, haverá substituição de títulos e provavelmente somente o último funcionará.

embora tenha prometido converter o DVD do MineCraft para iso, não sei o porque do mesmo apresentar erro, mas isso é assunto para outras 2 estórias.
