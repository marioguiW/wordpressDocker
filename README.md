# README

## Configuração Inicial

### Habilitar Métricas do Docker para Prometheus

Para que o Prometheus possa coletar as métricas do Docker corretamente, é necessário editar o arquivo `daemon.json` do Docker.

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

### Passo a passo

1. Clone o repositório:
   ```bash
   git clone https://github.com/marioguiW/wordpressDocker.git
   ```

2. Inicie os containers:
   ```bash
   docker compose up -d
   ```

3. Abra a URL:
   [http://localhost:8000/wp-login.php](http://localhost:8000/wp-login.php)

4. Faça login com as seguintes credenciais:
   - **Usuário**: root
   - **Senha**: root

### Tela Inicial do Wordpress

Após o login, você verá a tela inicial do Wordpress. Para instalar o plugin do Redis, siga os passos abaixo:

1. No menu lateral esquerdo, clique em **Plugins**.
2. Selecione **Adicionar Novo**.
3. Na barra de pesquisa, digite **Redis**.
4. Encontre o plugin Redis e clique em **Instalar Agora**.
5. Após a instalação, clique em **Ativar**.

Pronto! O plugin do Redis está instalado e ativo.

### Monitoramento com Prometheus

- Acesse o Link: [http://localhost:9090](http://localhost:9090)
- Navegue até Status -> Targets

### Conclusão

Fantástico! Seu ambiente está completamente configurado e operacional, integrando Wordpress, MySQL, Redis e Prometheus em containers Docker. Aproveite a eficiência e a flexibilidade proporcionadas por essa configuração robusta!