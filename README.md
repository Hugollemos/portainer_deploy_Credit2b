# GitHub Deploy Portainer

GitHub Action for deploying to Portainer.

## ENV Variables

- `API_URL`
- `API_KEY`
- `FILE_PATH`
- `STACK_NAME`

| Name          | Description               | Example                           |
| ------------- | ------------------------- | --------------------------------- |
| `API_URL`     | Endpoint URL  http ou https            | http://endpoint/api/stacks        |
| `API_KEY`     | Portainer token           | avc_9d76asd978a6sd9asdadakljsdgaksdgasasd= |
| `FILE_PATH`   | File path                 | "./docker-compose.yml"            |
| `STACK_NAME`  | Stack name                | front                             |

## How to Use

```yaml
      -
        name: Deploy to portainer
        uses: credit2b/portainer_deploy_Credit2b@v1
        env:
          API_URL: ${{ secrets.API_URL }}
          API_KEY: ${{ secrets.API_KEY }}
          FILE_PATH: "./stack-portal-cliente.yml"
          STACK_NAME: portalclient
          CONTAINER_NAME: portalclient   
          ENDPOINT: 2
          tags: credit2b/imagem:latest
          api_docker: ${{ secrets.api_docker }}
```
## Features
"This action creates a stack (docker-compose) in Portainer through the API. To create it, you will need the token created in Portainer, the correct endpoint, the name, and the path of the stack created in the project. The flow continues by sending the mentioned stacks to Portainer in the action. If the stack's name does not exist, it will create the stack. In subsequent times, it will check if it already exists; if yes, it will delete and recreate the stack, also removing the container and updating it.

This automated process is useful for ensuring the consistency and updating of stacks in the Portainer environment, facilitating the administration of containers and services in a project. The use of the authentication token and the correct endpoint is essential to ensure security and proper connectivity with Portainer, enabling actions to be executed effectively and precisely."


---
"Esta ação cria uma pilha (docker-compose) no Portainer por meio da API. Para criá-la, você precisará do token criado no Portainer, do endpoint correto, do nome e do caminho da pilha criada no projeto. O fluxo continua enviando as pilhas mencionadas para o Portainer na ação. Se o nome da pilha não existir, ela será criada. Nas vezes subsequentes, verificará se já existe; se sim, excluirá e recriará a pilha, removendo também o contêiner e atualizando-o.

Esse processo automatizado é útil para garantir a consistência e a atualização das pilhas no ambiente do Portainer, facilitando a administração de contêineres e serviços em um projeto. O uso do token de autenticação e do endpoint correto é essencial para garantir a segurança e a conectividade adequada com o Portainer, permitindo que as ações sejam executadas de maneira eficaz e precisa."
## License
