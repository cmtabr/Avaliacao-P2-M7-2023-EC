# Template para avaliação P2

Saída esperada após execução do programa:

<img src="./media/tela-front.png" display="flex">

# Relatório: 
Para iniciar foram criadas duas instâncias EC2 (foto abaixo), sendo a primeira para comportar os arquivos státicos servidos pelo apache e a segunda para gerenciar o backend, fazendo conexão do banco de dados e atualizando novas informações para o frontend.
![image](https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC/assets/99201276/a03228f3-41ae-4baa-b325-99075704cd78)

Na instância do front foram realizados os comandos abaixo
```
sudo apt update && sudo apt upgrade
sudo apt install apache2 
git clone https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC.git
sudo cp -r ./Avaliacao-P2-M7-2023-EC/frontend /var/www/html
```

Com o front rodando nesta instância foram feitas alterações no arquivo script.js para alterar os endpoints do backend que eram acessados para o IP abaixo: 
http://54.209.58.232

O backend por sua vez foi alterado para acessar a instância do rds realizada (imagem abaixo). No endpoint p2-db-postgres.ctzzjjlrmc0k.us-east-1.rds.amazonaws.com, fazemos a conexão com o rds e então criamos a tabela minhas_notas para armazenar os dados enviados pelo frontend.
![image](https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC/assets/99201276/22bd3d67-d8af-4c83-a696-685d1f0f2ddd)

Utilizando o comando: 
```
python3 criar_banco.py
```
Criamos a tabela e então o banco está pronto para receber os dados

Podemos ver os dados na foto abaixo: 

![image](https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC/assets/99201276/c287b2c4-05ae-4bc9-bdc2-f8ef832ec752)

Além disso foram criados IP's elásticos para ambas as instâncias. 

![image](https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC/assets/99201276/889e6523-5795-4bb4-8188-fca2a4e397af)

Por fim temos a saída da aplicação: 

![image](https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC/assets/99201276/d424366c-2a1a-4358-b555-4819960eaee3)


Vídeo de comprovação da funcionalidade: 

[Screencast from 2023-09-29 16-00-47.webm](https://github.com/cmtabr/Avaliacao-P2-M7-2023-EC/assets/99201276/0ec1d54d-fd00-4969-943a-263ef32b504c)

