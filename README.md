# Ansible Django Deploy
Este é um projeto Ansible para facilitar o deployment de aplicações Django. Ele automatiza várias tarefas comuns, como a instalação de dependências, migrações de banco de dados, coleta de arquivos estáticos e reinicialização do servidor.

## Pré-requisitos
Certifique-se de que os seguintes requisitos estejam instalados na máquina de destino:

Python 3.x
Ansible
Git
Como usar
1. Clone este repositório:

```bash
git clone https://github.com/leovoltz/ansible-django-deploy.git
```
2. Navegue até o diretório do projeto:

```bash
cd ansible-django-deploy
```
3. Edite o arquivo inventory.ini e adicione os detalhes do seu servidor:

```ini
[servers]
servidor ansible_host=SEU_ENDERECO_IP ansible_user=SEU_USUARIO ansible_ssh_private_key_file=CAMINHO_PARA_CHAVE_PRIVADA
```
4. Configure as variáveis no arquivo vars.yml conforme necessário.

5. Execute o playbook Ansible:

```bash
ansible-playbook -i inventory.ini deploy.yml
```
Este playbook realizará as seguintes etapas:

- Atualizar o sistema operacional.
- Instalar as dependências necessárias, como o Python, o virtualenv e o supervisor.
- Configurar as variáveis de ambiente da aplicação.
- Clonar o repositório do Django.
- Instalar as dependências do Django usando o pip.
- Realizar migrações de banco de dados.
- Coletar arquivos estáticos.
- Configurar e iniciar o serviço do supervisor para executar a aplicação.

## Notas adicionais
- Certifique-se de ajustar as variáveis no arquivo vars.yml de acordo com as necessidades do seu projeto.
- Este playbook assume que você está usando o Nginx como servidor web. Se você estiver usando um servidor diferente, ajuste a configuração conforme necessário.
- Sempre revise e ajuste a segurança do seu servidor antes de colocar um aplicativo em produção.

## Contribuindo
Se você encontrar problemas ou tiver sugestões de melhorias, sinta-se à vontade para abrir uma issue ou enviar um pull request. Sua contribuição é bem-vinda!
