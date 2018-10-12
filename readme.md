## Recursos disponiveis
        1.Nginx
        2.Gitea (localhost:8000)
        3.Jenkins(localhost:8080)
        4.PhpMyAdmin (localhost:8080)
        5.SonarQube (localhost:9000)
        6.Mysql 5.7 
		7.Postgres
    
## Como usar o docker ? 
	1 - Acesse a pasta onde está o arquivo docker-compose.yml, e utilize o seguinte comando para iniciar os container: docker-compose up -d 
		(nota: as configurações dos containes, estão especificadas no arquivo .yml)

## Nginx
	Voce pode configurar o nginx para facilitar o acesso aos constainer. Por exemplo, em vez de acessar o gitea via localhost:8000, voce pode configurar uma URL amigável no nginx, por exemlo: gitea.company.com.br
	
## Problemas para start no container no Jenkins ?
	1 - O diretorio /data/jenkins é criado pelo docker ao instanciar o container. Voce ja deve ter percebido que alterações no 
		direotorio /data exigem permissoes de root (sudo). Caso ao realizar start do container tenha o seguinte erro:
			touch cannot touch '/var/jenkins_home/copy_reference_file.log': Permission denied
		Para resolver o problema altere o proprietario da pasta, atraves do comadno chown, por exemplo: chown seu_nome_de_usuario jenkins/

## Como acessar o Banco de dados Mysql usando docker ? 

	1 - Acesse o container utilizando o seguinte comando:  docker container exec -it bd_mysql bash
	2 - Dentro do container, voce pode acessar o mysql e usar comando sql, utilizando o seguinte comando: mysql -h localhost -u gitea -p
	3 - Exemplo: show databases; (irá listar todas as databases criadas no seu mysql)
