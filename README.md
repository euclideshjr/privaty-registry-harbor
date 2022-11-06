## Projeto visa a criação em laboratório de um Registry Privado com Harbor.  

- ## Procedimentos executados durante a execução desse Playbook:  
- [X] Verifica se os diretório e certificados existem antes da execução  
- [X] Instala Docker  
- [X] Instala Docker-Compose  
- [X] Cria os diretórios para os certificados  
- [X] Cria o diretório usado como volume bind para o Harbor  
- [X] Cria todos os certificados necessários para o deploy do Harbor.  
- [X] Move os certificados para os diretórios necessários.  
- [X] Baixa e faz o deploy do Harbor.  

- ## As credenciais de acesso iniciais para o Harbor são: 
- **usuario:** admin
- **senha:** "definida no arquivo external\_vars/credentials.yml"  
&nbsp;
> ## Para execução do Playbook é necessário que se tenha o ansible instalado no seu pc.  
## Utilização:  
- Editar o arquivo hosts e informar o IP do servidor Harbor.  

- Editar o arquivo external\_vars/parametros.yml e informar o valor das variaveis  

- Editar o arquivo external\_vars/credentials.yml e informar o valor das variáveis  

- Como sugestão, após edição, encryptar o arquivo credentials.yml. Será solicitado que informe uma senha e a confirme para criptografar o conteúdo do arquivo.
```
ansible-vault encrypt external_vars/credentials.yml
```  

- No diretório raiz do repositório executar, caso tenha criptografado o arquivo:
```
ansible-playbook -i hosts playbook-harbor.yml --ask-vault-pass
``` 

- Caso não tenha criptografado o arquivo do vault:
```
ansible-playbook -i hosts playbook.yml
```
