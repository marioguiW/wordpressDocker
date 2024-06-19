# README

## Configuração Inicial

### Liberar Métricas do Docker para Prometheus

Para permitir que o Prometheus leia corretamente as métricas do Docker, é necessário editar o arquivo `daemon.json` do Docker.

- **No Windows**: `%programdata%\docker\config\daemon.json`
- **No Linux**: `/etc/docker/daemon.json`
- **No macOS**: `~/.docker/daemon.json`

Adicione a seguinte configuração:

```json
{
  "experimental": false,
  "metrics-addr": "127.0.0.1:9323"
}
```

Após realizar essa alteração, reinicie o Docker para aplicar as mudanças.

### Passo a Passo

1. Clone o repositório:
   ```bash
   git clone https://github.com/marioguiW/wordpressDocker.git
   ```

2. Execute o container:
   ```bash
   docker compose up -d
   ```

3. Para acessar a página de login do Wordpress que já está configurada, acesse a URL:
   [http://localhost:8000/wp-login.php](http://localhost:8000/wp-login.php)

4. Faça login com as seguintes credenciais:
   - **Usuário**: root
   - **Senha**: root

### Tela Inicial do Wordpress

Após o login, você verá a tela inicial do Wordpress. Para instalar o plugin do Redis, siga os passos abaixo:

	1.	No menu lateral esquerdo, clique em Plugins.
	2.	Selecione Adicionar Novo.
	3.	Na barra de pesquisa, digite Redis.
	4.	Encontre o plugin Redis e clique em Instalar Agora.
	5.	Após a instalação, clique em Ativar.

Pronto! O plugin do Redis está instalado e ativo.


### Monitoramento do Docker com Prometheus

1. Acesse a URL: [http://localhost:9090](http://localhost:9090)
2. Navegue até `Status > Targets`

### Conclusão

Parabéns! Agora você possui um ambiente totalmente configurado com Wordpress, MySQL, Redis e Prometheus operando em containers Docker.
