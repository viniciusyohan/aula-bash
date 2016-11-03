# aula-bash
#!/bin/bash
# Escrito por Vinicius Dreyer


principal() {           # Fun��o principal do programa
    clear               # limpa a tela
echo "[1]Mostrar a localiza��o atual do usu�rio no sistema de arquivos''
echo "[2]  Mostrar o tipo de um arquivo''
echo "[3] Criar um diret�rio''
echo "[4] Apagar um diret�rio n�o vazio''
echo "[5] ler 2 n�meros e indicar qual � o maior deles e qual � o menor''
echo "[6]  Exibir as �ltimas linhas de um arquivo(pedir ao usu�rio a quantidade de linhas a
mostrar''
echo "[7] Exibir as primeiras linhas de um arquivo(pedir ao usu�rio a quantidade de linhas a
mostrar''
echo "[8]  Mostrar a localiza��o de um comando espec�fico utilizar which ou whereis''
echo "[9]  Mostra um diret�rio informado pelo usu�rio em formato de �rvore (instalar comando
tree''
echo "[10]  Copiar um arquivo para um outro diret�rio (usu�rio deve informar qual � o arquivo e
qual � o diret�rio''
echo "[11] Mover um arquivo para outro diret�rio''
echo "[12] Sair"
echo
echo -n "Qual a opcao desejada ? "
    read opcao          # faz a leitura da vari�vel "opcao", 
                        # que ser� utilizada no comando case
                        # para indicar qual a op��o a ser utilizada

                        # caso o valor da vari�vel "opcao"...
    case $opcao in
        1)              # seja igual a "1", ent�o fa�a as instru��es abaixo
            clear
           sudo pwd    # Localiza o arquivo"
        2)
            clear
            ls --  # comando que exibe o tipo de arquivo
        
	3)
	clear
	mkdir #comando que cria um diret�rio

	4)clear
	rm -Rf <directory> #comando que remove arquivos n�o vazios

	5)clear
	#Verifica se um nmero � maior, menor ou igual a outro

	a=6
	b=3

	if [ $a -lt $b ]
	then
   	echo '$a � menor que $b!'
	elif [ $a -gt $b ]
	then
  	 echo '$a � maior que $b!'
	elif [ $a -eq $b ]
	then
  	 echo '$a � igual a $b!'
	fi

	6)clear
	tail -n "Arquivo_Exemplo" | grep -n ^ | grep ^7 #comando para exibir as ultimas linhas de arquivo, pedindo ao usu�rio o numero de linhas

	7)clear
	head -$p2 $p1 #comando para exibir as primeira linhas do arquivo

	8)clear 
	$witch clear #exibe o caminho do comando clear
	
	9)clear 
	ls <diretorio>tree #exibe o diretorio em formato tree
	
	10)clear
	cp arquivo-origem arquivo-destino #copia o arquivo para conforme origem e destino definido pelo usuario.

	11)clear
	mv arquivo-origem arquivo-destino #move o arquivo para conforme origem e destino definido pelo usuario.
	









	12)
            clear
            exit ;;
        *)              # esta op�ao existe para caso o usu�rio digite um 
                        # valor diferente de 1, 2,3,4,5,6,7,8,9,10,11 ou 12
            opcao_invalida ;;
    esac
}

laranja() {             # fun��o da op��o laranja
    echo "Laranja"
    read pause          # usado para pausar a execu��o do script
    principal           # volta para a fun��o principal
}

martelo() {             # fun��o da op��o martelo
    clear
    echo "Martelo"
    read pause
    principal
}

opcao_invalida() {      # fun��o da op��o inv�lida
    clear
    echo "Opcao desconhecida."
    read pause
    principal
}

principal               # o script come�a aqui, as fun��es das linhas anteriores
                        # s�o lidas pelo interpretador bash e armazenadas em mem�ria.

                        # o bash n�o tem como adivinhar qual das fun��es ele deve 
                        # executar, por isto o a execu��o do script realmente come�a
                        # quando aparece uma instru��o fora de uma fun��o, neste caso,
