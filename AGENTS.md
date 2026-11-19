# AGENTS.md - MYNSTR

Leia [README.md](README.md) e os documentos relacionados ao escopo solicitado. O projeto permanece na fase de documentação e validação; esta regra não autoriza implementação, instalação ou uso de serviços pagos.

## Execução no Windows e no servidor (decisão do Hil em 28/10/2026)

- Esta decisão substitui orientações anteriores que recomendem PowerShell, inclusive exemplos em documentos relacionados.
- Não executar comandos, scripts, diagnósticos ou alterações pelo PowerShell. Seu único uso permitido neste fluxo é abrir uma sessão SSH interativa, sem comando remoto anexado.
- Depois de conectar, executar os comandos do servidor dentro do shell Linux dessa sessão, em passos curtos, legíveis e verificáveis, respeitando as aprovações do projeto.
- Não executar operações do servidor a partir do Windows por `ssh host "comando"`, encadeamentos, pipelines, scripts intermediários ou payloads codificados (por exemplo, Base64 seguido de `exec`). Usar outro interpretador local não contorna esta regra.
- Para leitura e edição de arquivos locais, usar ferramentas diretas de arquivos, sem PowerShell. Uma necessidade específica de execução local no Windows deve ser apresentada separadamente ao Hil antes de executar.
- Falha de ferramenta ou do ambiente não autoriza trocar este fluxo por execução remota disparada do Windows. Informar a limitação e preservar as proteções existentes.
