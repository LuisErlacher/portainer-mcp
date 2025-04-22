# Guia para Compilar o Portainer MCP no Windows

Este guia descreve os passos para compilar o servidor `portainer-mcp` a partir do código-fonte neste repositório em um ambiente Windows.

## Pré-requisitos

1.  **Instalar o Go:**
    *   Baixe e instale a versão mais recente do Go para Windows a partir do site oficial: [https://go.dev/dl/](https://go.dev/dl/)
    *   Siga as instruções de instalação. Geralmente, isso envolve executar o instalador `.msi`.
    *   Verifique se o Go foi instalado corretamente abrindo um Prompt de Comando (`cmd.exe`) ou PowerShell e digitando: `go version`. Você deve ver a versão instalada.

2.  **Git (Opcional, se precisar clonar):**
    *   Se você ainda não tem o código-fonte, instale o Git para Windows: [https://git-scm.com/download/win](https://git-scm.com/download/win)
    *   Clone o repositório (se necessário): `git clone https://github.com/portainer/portainer-mcp.git`

## Passos para Compilação

1.  **Navegue até o Diretório do Projeto:**
    *   Abra um Prompt de Comando ou PowerShell.
    *   Use o comando `cd` para navegar até o diretório onde você clonou ou onde se encontra o código-fonte do `portainer-mcp`.
    *   Exemplo: `cd C:\Users\SeuUsuario\Documentos\portainer-mcp`

2.  **Compile o Projeto:**
    *   Execute o comando de compilação do Go. Este comando irá compilar o código que está no diretório `cmd/portainer-mcp` e gerar um executável chamado `portainer-mcp.exe` no diretório atual.
    ```bash
    go build -o portainer-mcp.exe ./cmd/portainer-mcp
    ```

3.  **Verifique o Executável:**
    *   Após a compilação (que pode levar alguns segundos), você encontrará o arquivo `portainer-mcp.exe` no diretório raiz do projeto.

## Próximos Passos

*   Você pode mover o `portainer-mcp.exe` para um local mais conveniente (ex: `C:\Program Files\portainer-mcp\` ou um diretório no seu `PATH`).
*   Atualize o arquivo `.cursor/rules/mcp.json` para apontar para o caminho correto onde você colocou o `portainer-mcp.exe`.
*   Execute o servidor a partir do terminal para testar, usando os argumentos apropriados (servidor Portainer, token, etc.), por exemplo:
    ```bash
    C:\path\to\portainer-mcp.exe -server seu.portainer.host:9443 -token seu_token_aqui -tools "%TEMP%\portainer-tools.yaml"
    ```
