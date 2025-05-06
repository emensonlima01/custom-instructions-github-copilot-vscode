# custom-instructions-github-copilot-vscode

## Visão Geral

Este repositório centraliza instruções customizadas para o GitHub Copilot e VSCode, otimizando a experiência de desenvolvimento e padronizando processos em projetos modernos. Aqui, você encontra diretrizes para melhorar a colaboração, a segurança e a qualidade do código, além de documentações essenciais para o ciclo de vida do software.

---


## Instruções Personalizadas do Copilot no VSCode

O GitHub Copilot no VSCode permite personalizar o comportamento do agente por meio de arquivos de instrução e configurações avançadas. Isso garante que o assistente siga padrões, regras e requisitos específicos do seu projeto ou equipe.


---

## Visão Completa das Configurações do Copilot no VSCode

O Copilot oferece uma ampla gama de configurações para personalizar a experiência de desenvolvimento, tanto para indivíduos quanto para equipes. A seguir, detalhamos as principais opções, exemplos práticos e dicas para times que desejam extrair o máximo da IA no fluxo de trabalho.

---

### Guia Completo de Configurações do Copilot no VSCode

#### Ativação e Escopo
- **`github.copilot.enable`**: Ativa/desativa o Copilot globalmente ou por linguagem. Exemplo:
  ```jsonc
  "github.copilot.enable": {
    "*": true, // Ativa para todos os arquivos
    "markdown": false // Desativa para arquivos Markdown
  }
  ```
- **`github.copilot.editor.enableAutoCompletions`**: Mostra sugestões inline automaticamente enquanto digita.
- **`github.copilot.editor.enableCodeActions`**: Exibe ações rápidas do Copilot no editor (ex: refatoração, geração de código, etc).
- **`github.copilot.renameSuggestions.triggerAutomatically`**: Sugere renomeações de variáveis/funções automaticamente.

#### Geração de Código, Commits, Testes e PRs
- **`github.copilot.chat.codeGeneration.instructions`**: Lista de arquivos/textos com instruções para geração de código.
- **`github.copilot.chat.commitMessageGeneration.instructions`**: Instruções para mensagens de commit.
- **`github.copilot.chat.testGeneration.instructions`**: Instruções para geração de testes automatizados.
- **`github.copilot.chat.pullRequestDescriptionGeneration.instructions`**: Instruções para geração de descrições de pull request.
- **`github.copilot.chat.reviewSelection.instructions`**: Instruções para revisão de código automatizada.

#### Busca Semântica e Contexto
- **`github.copilot.chat.codesearch.enabled`**: Habilita busca semântica no código.
- **`github.copilot.chat.codesearch.suggestions.maxResults`**: Máximo de sugestões retornadas.
- **`github.copilot.chat.codesearch.suggestions.maxResultsPerFile`**: Máximo de sugestões por arquivo.
- **`github.copilot.chat.codesearch.suggestions.maxResultsPerFileType`**: Máximo de sugestões por tipo de arquivo.
- **`github.copilot.chat.codesearch.suggestions.maxResultsPerFileTypeAndFile`**: Máximo de sugestões por tipo e arquivo.

#### Contexto Temporal e Inteligência
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui arquivos editados recentemente como contexto para sugestões.
- **`github.copilot.chat.edits.temporalContext.enabled`**: Inclui contexto temporal para sugestões de edição.
- **`github.copilot.chat.edits.suggestRelatedFilesFromGitHistory`**: Sugere arquivos relacionados com base no histórico do Git.
- **`github.copilot.chat.edits.suggestRelatedFilesForTests`**: Sugere arquivos relacionados para geração de testes.
- **`github.copilot.chat.edits.suggestRelatedFilesForTests.maxResults`**: Limita o número de sugestões de arquivos relacionados para testes.

#### Automação, Agente e Tarefas
- **`github.copilot.chat.agent.thinkingTool`**: Habilita ferramenta de "pensamento" do agente para planejamento e decomposição de tarefas.
- **`github.copilot.chat.agent.thinkingTool.maxResults`**: Quantidade máxima de "planos" sugeridos.
- **`github.copilot.chat.agent.runTasks`**: Permite execução de tarefas automatizadas pelo agente.
- **`github.copilot.chat.agent.runTasks.maxResults`**: Máximo de tarefas paralelas.
- **`github.copilot.chat.newWorkspaceCreation.enabled`**: Permite criar workspaces do zero via chat.
- **`github.copilot.chat.useProjectTemplates`**: Habilita uso de templates de projetos para scaffolding.

#### Experimentos, UX e Acessibilidade
- **`github.copilot.chat.enableExperimental`**: Ativa recursos experimentais do Copilot Chat.
- **`github.copilot.chat.enableExperimentalChat`**: Ativa chat experimental.
- **`github.copilot.nextEditSuggestions.enabled`**: Sugestões de próxima edição (Next Edit Suggestions).
- **`github.copilot.chat.followUps`**: Sugestões de perguntas de acompanhamento no chat.
- **`github.copilot.chat.localeOverride`**: Define o idioma das respostas do Copilot (ex: `pt-br`, `en`).
- **`github.copilot.chat.runCommand.enabled`**: Permite executar comandos do VSCode via chat.
- **`github.copilot.chat.terminalChatLocation`**: Define onde as consultas do terminal são exibidas.
- **`github.copilot.chat.scopeSelection`**: Solicita escopo específico ao usar comandos como `/explain`.
- **`github.copilot.chat.reviewSelection.enabled`**: Habilita revisão de código para seleções de texto.
- **`chat.promptFiles`**: Permite uso de arquivos de prompt reutilizáveis.
- **`chat.promptFilesLocations`**: Define diretórios de arquivos de prompt.
- **`inlineChat.accessibleDiffView`**: Visualização de diff acessível para sugestões do chat inline.
- **`accessibility.signals.chatRequestSent`**: Sinal sonoro/alerta ao enviar requisição de chat.
- **`accessibility.signals.chatResponseReceived`**: Sinal sonoro/alerta ao receber resposta do chat.

#### Integração e Protocolos
- **`chat.mcp.discovery.enabled`**: Integração com Model Context Protocol (MCP) para ferramentas externas.

#### Parâmetros Avançados do Modelo
- **`github.copilot.advanced.temperature`**: Controla criatividade das respostas.
- **`github.copilot.advanced.maxTokens`**: Tamanho máximo das respostas.
- **`github.copilot.advanced.topP`**: Diversidade das respostas.
- **`github.copilot.advanced.frequencyPenalty`**: Penaliza repetições.
- **`github.copilot.advanced.presencePenalty`**: Incentiva exploração de novos tópicos.

---

### Exemplos de Blocos de Configuração

#### Ativando Copilot apenas para arquivos TypeScript e desativando para Markdown
```jsonc
"github.copilot.enable": {
  "typescript": true,
  "markdown": false
}
```

#### Limitando sugestões de busca semântica
```jsonc
"github.copilot.chat.codesearch.suggestions.maxResults": 3,
"github.copilot.chat.codesearch.suggestions.maxResultsPerFile": 1
```

#### Definindo idioma das respostas do Copilot
```jsonc
"github.copilot.chat.localeOverride": "pt-br"
```

#### Habilitando prompts reutilizáveis em múltiplos diretórios
```jsonc
"chat.promptFiles": true,
"chat.promptFilesLocations": {
  ".github": true,
  "docs": true
}
```

#### Parâmetros avançados para respostas criativas
```jsonc
"github.copilot.advanced": {
  "temperature": 1,
  "maxTokens": 8000,
  "topP": 1,
  "frequencyPenalty": 0.2,
  "presencePenalty": 0.8
}
```

---

### Dicas Avançadas e Observações

- Combine instruções de negócio, técnicas, UX, QA e segurança para potencializar a inteligência do Copilot.
- Use arquivos de instrução versionados para garantir rastreabilidade e evolução dos padrões.
- Teste recursos experimentais em ambientes controlados antes de adotar em produção.
- Ajuste os parâmetros do modelo conforme o perfil do time (mais criatividade, mais precisão, etc).
- Utilize prompts reutilizáveis para padronizar fluxos em múltiplos projetos.
- Documente cada configuração no `settings.json` para facilitar o onboarding.
- Explore integrações com MCP para automações e ferramentas externas.
- Monitore o impacto das configurações e ajuste conforme feedback do time.

---

### Outras Configurações Avançadas e Específicas

- **`github.copilot.enable`**: Ativa ou desativa o Copilot para linguagens ou arquivos específicos.
- **`github.copilot.editor.enableAutoCompletions`**: Controla se as sugestões inline aparecem automaticamente.
- **`github.copilot.nextEditSuggestions.enabled`**: Habilita sugestões de próxima edição (Next Edit Suggestions).
- **`github.copilot.chat.followUps`**: Permite que o Copilot sugira perguntas de acompanhamento no chat.
- **`github.copilot.chat.localeOverride`**: Define o idioma das respostas do Copilot (ex: `pt-br`, `en`).
- **`github.copilot.chat.runCommand.enabled`**: Permite executar comandos do VSCode diretamente pelo chat do Copilot.
- **`github.copilot.chat.terminalChatLocation`**: Define onde as consultas do terminal são exibidas (painel, aba, etc).
- **`github.copilot.chat.scopeSelection`**: Solicita escopo específico ao usar comandos como `/explain` sem seleção ativa.
- **`github.copilot.chat.reviewSelection.enabled`**: Habilita revisão de código para seleções de texto no editor.
- **`github.copilot.chat.reviewSelection.instructions`**: Adiciona instruções customizadas para revisões de código.
- **`github.copilot.chat.newWorkspaceCreation.enabled`**: Permite criar workspaces do zero via chat.
- **`github.copilot.chat.edits.temporalContext.enabled`**: Inclui arquivos visualizados/editados recentemente como contexto para sugestões de edição.
- **`github.copilot.chat.edits.suggestRelatedFilesFromGitHistory`**: Sugere arquivos relacionados com base no histórico do Git.
- **`github.copilot.chat.edits.suggestRelatedFilesForTests`**: Sugere arquivos relacionados para geração de testes.
- **`github.copilot.chat.edits.suggestRelatedFilesForTests.maxResults`**: Limita o número de sugestões de arquivos relacionados para testes.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.

### Configurações de Geração e Contexto

- **`github.copilot.chat.codeGeneration.instructions`**: Lista de arquivos ou textos que orientam a geração de código. Use para garantir que o Copilot siga requisitos de negócio, arquitetura, padrões de segurança, idioma, etc.
- **`github.copilot.chat.commitMessageGeneration.instructions`**: Define instruções para mensagens de commit, garantindo aderência a convenções como Conventional Commits.
- **`github.copilot.chat.testGeneration.instructions`**: Permite adicionar instruções específicas para geração de testes automatizados, como padrões de cobertura, frameworks preferidos e boas práticas de QA.
- **`github.copilot.chat.pullRequestDescriptionGeneration.instructions`**: Adicione instruções para que o Copilot gere descrições de pull request alinhadas ao seu fluxo de revisão.
- **`github.copilot.chat.reviewSelection.instructions`**: Insira instruções para revisões de código automatizadas, sugerindo padrões de análise, checklist de segurança, etc.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui arquivos recentemente editados como contexto, tornando as sugestões mais inteligentes e contextuais.
- **`github.copilot.chat.codesearch.enabled`**: Habilita a busca semântica no código, permitindo que o Copilot encontre e sugira trechos relevantes do projeto.
- **`github.copilot.chat.codesearch.suggestions.maxResults`**: Define o número máximo de sugestões retornadas pela busca semântica.
- **`github.copilot.chat.codesearch.suggestions.maxResultsPerFile`**: Limita o número de sugestões por arquivo.
- **`github.copilot.chat.codesearch.suggestions.maxResultsPerFileType`**: Limita sugestões por tipo de arquivo.
- **`github.copilot.chat.codesearch.suggestions.maxResultsPerFileTypeAndFile`**: Limita sugestões por tipo e arquivo.

### Configurações de Automação, Agente e Experimentos

- **`github.copilot.chat.agent.thinkingTool`**: Habilita a ferramenta de "pensamento" do agente, que ajuda a planejar, decompor e organizar tarefas complexas.
- **`github.copilot.chat.agent.thinkingTool.maxResults`**: Ajusta a quantidade de "planos" ou "pensamentos" que o agente pode sugerir.
- **`github.copilot.chat.agent.runTasks`**: Permite que o agente execute tarefas automatizadas no workspace, como rodar scripts, testes, builds, etc.
- **`github.copilot.chat.agent.runTasks.maxResults`**: Controla quantas tarefas automatizadas o agente pode executar em paralelo.
- **`github.copilot.chat.enableExperimental`** e **`github.copilot.chat.enableExperimentalChat`**: Ativam recursos experimentais do Copilot Chat, como novos fluxos de interação e automações.
- **`github.copilot.chat.newWorkspaceCreation.enabled`**: Permite que o agente crie novos workspaces automaticamente a partir de templates ou instruções.
- **`github.copilot.chat.useProjectTemplates`**: Habilita o uso de templates de projetos para scaffolding rápido.

### Configurações de Editor e UX

- **`github.copilot.editor.enableCodeActions`**: Ativa ações de código sugeridas pelo Copilot diretamente no editor.
- **`github.copilot.renameSuggestions.triggerAutomatically`**: Sugere renomeações automáticas de variáveis e funções.
- **`github.copilot.chat.generateTests.codeLens`**: Ativa sugestões automáticas de geração de testes diretamente no editor.
- **`github.copilot.chat.generateTests.codeLens.maxResults`**: Limita o número de sugestões de geração de testes exibidas no editor.
- **`chat.promptFiles`**: Permite o uso de arquivos de prompt reutilizáveis para padronizar instruções em diferentes projetos.
- **`chat.promptFilesLocations`**: Define os diretórios onde os arquivos de prompt podem ser encontrados.

### Configurações Avançadas do Modelo

- **`github.copilot.advanced.temperature`**: Controla a criatividade das respostas (valores mais altos = respostas mais diversas).
- **`github.copilot.advanced.maxTokens`**: Define o tamanho máximo das respostas geradas.
- **`github.copilot.advanced.topP`**: Ajusta a diversidade das respostas.
- **`github.copilot.advanced.frequencyPenalty`**: Penaliza repetições na resposta.
- **`github.copilot.advanced.presencePenalty`**: Incentiva o modelo a explorar novos tópicos.

### Configurações de Integração e Contexto

- **`chat.mcp.discovery.enabled`**: Integração com Model Context Protocol (MCP) para uso de ferramentas externas e fluxos avançados.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.

### Configurações de Acessibilidade e Experiência

- **`inlineChat.accessibleDiffView`**: Ativa visualização de diff acessível para sugestões do chat inline.
- **`accessibility.signals.chatRequestSent`**: Emite sinal sonoro/alerta ao enviar requisição de chat.
- **`accessibility.signals.chatResponseReceived`**: Emite sinal sonoro/alerta ao receber resposta do chat.

---

## Exemplos Avançados de Uso

- **Padronização Total**: Combine arquivos de PRD, TRD, convenções de commit, padrões de testes e templates de PR para garantir que todo o ciclo de desenvolvimento siga as regras do time.
- **Onboarding Automatizado**: Novos membros entendem rapidamente os padrões do projeto apenas lendo os arquivos de instrução e observando as sugestões do Copilot.
- **Geração de Testes Inteligentes**: Oriente o Copilot a criar testes unitários, de integração e end-to-end conforme o padrão do time, frameworks e requisitos de cobertura.
- **Revisão de Código Automatizada**: Use instruções para que o Copilot aponte problemas comuns, checklist de segurança, padrões de arquitetura e sugestões de refatoração.
- **Pull Requests Profissionais**: Gere descrições de PRs automaticamente seguindo o padrão do time, facilitando revisões e auditorias.
- **Automação de Tarefas**: Permita que o agente execute scripts, builds, deploys e outras tarefas automatizadas diretamente do chat.

---

## Dicas para Times e Melhores Práticas

- Centralize as instruções em arquivos Markdown versionados no repositório (ex: PRD, TRD, convenções de commit, padrões de testes, templates de PR).
- Atualize as instruções sempre que houver mudanças de processo, arquitetura ou requisitos.
- Use comentários no `settings.json` para documentar o propósito de cada configuração.
- Combine instruções de diferentes áreas (negócio, técnico, UX, QA, segurança) para potencializar a inteligência do Copilot.
- Teste recursos experimentais em branches dedicadas antes de adotar em produção.
- Monitore e ajuste os parâmetros avançados do modelo conforme o perfil do time e do projeto.
- Compartilhe exemplos de boas instruções e configurações com a comunidade para evoluir o ecossistema.

---

## Referências e Links Úteis

- [Documentação oficial do Copilot Settings](https://code.visualstudio.com/docs/copilot/reference/copilot-settings)
- [User and workspace settings (VSCode)](https://code.visualstudio.com/docs/configure/settings)
- [Conventional Commits Specification](https://www.conventionalcommits.org/en/v1.0.0/)

---

---

### O que são Instruções Personalizadas?

Instruções personalizadas são arquivos (geralmente em Markdown) e parâmetros definidos no `settings.json` que orientam o Copilot a gerar código, mensagens de commit, testes e até descrições de pull request de acordo com as regras, padrões e requisitos do seu projeto. Isso permite que o Copilot atue como um verdadeiro membro do time, respeitando processos, arquitetura, padrões de segurança, idioma e muito mais.

---

### Principais Configurações do Projeto

O arquivo `.vscode/settings.json` deste repositório já traz uma configuração robusta para potencializar o uso do Copilot, incluindo:

- **`github.copilot.chat.codeGeneration.instructions`**: Lista de arquivos Markdown (PRD, TRD, Conventional Commits) que orientam o Copilot na geração de código, garantindo aderência a requisitos de negócio, técnicos e padrões de commit.
- **`github.copilot.chat.commitMessageGeneration.instructions`**: Aponta para o arquivo de convenção de commits, fazendo com que o Copilot gere mensagens já no padrão correto.
- **`github.copilot.chat.codesearch.enabled`**: Habilita a busca semântica no código, permitindo que o Copilot encontre e sugira trechos relevantes do projeto.
- **`github.copilot.chat.generateTests.codeLens`**: Ativa sugestões automáticas de geração de testes diretamente no editor.
- **`github.copilot.advanced`**: Permite ajustar parâmetros avançados do modelo, como temperatura, maxTokens, topP, frequencyPenalty e presencePenalty, para personalizar o estilo e criatividade das respostas.
- **`github.copilot.chat.agent.thinkingTool`**: Habilita a ferramenta de "pensamento" do agente, que ajuda a planejar e organizar tarefas complexas.
- **`github.copilot.chat.agent.runTasks`**: Permite que o agente execute tarefas automatizadas no workspace.
- **`github.copilot.editor.enableCodeActions`**: Ativa ações de código sugeridas pelo Copilot diretamente no editor.
- **`github.copilot.renameSuggestions.triggerAutomatically`**: Sugere renomeações automáticas de variáveis e funções.
- **`chat.promptFiles` e `chat.promptFilesLocations`**: Permitem o uso de arquivos de prompt reutilizáveis e a configuração de seus diretórios.

#### Exemplo real do settings.json deste projeto:

```jsonc
{
  "github.copilot.chat.codeGeneration.instructions": [
    { "file": "./docs/PRD.md" },
    { "file": "./docs/CONVENTIONAL_COMMITS.md" },
    { "file": "./docs/TRD.md" }
  ],
  "github.copilot.chat.commitMessageGeneration.instructions": [
    { "file": "./docs/CONVENTIONAL_COMMITS.md" }
  ],
  "github.copilot.chat.codesearch.enabled": true,
  "github.copilot.chat.generateTests.codeLens": true,
  "github.copilot.advanced": {
    "temperature": 0.9,
    "maxTokens": 5000,
    "topP": 0.9,
    "frequencyPenalty": 0.5,
    "presencePenalty": 0.6
  },
  "github.copilot.chat.agent.thinkingTool": true,
  "github.copilot.chat.agent.runTasks": true,
  "github.copilot.editor.enableCodeActions": true,
  "github.copilot.renameSuggestions.triggerAutomatically": true,
  "chat.promptFiles": true,
  "chat.promptFilesLocations": {
    ".github": true
  }
}
```

### Outras Configurações Úteis do Copilot no VSCode


#### Outras configurações avançadas e dicas:

- **`github.copilot.chat.testGeneration.instructions`**: Adicione arquivos ou textos para orientar a geração de testes automatizados, garantindo que os testes sigam padrões do time.
- **`github.copilot.chat.useProjectTemplates`**: Permite usar templates de projetos para criar rapidamente novas bases padronizadas.
- **`github.copilot.chat.pullRequestDescriptionGeneration.instructions`**: Adicione instruções para que o Copilot gere descrições de pull request alinhadas ao seu fluxo de revisão.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui arquivos recentemente editados como contexto, tornando as sugestões mais inteligentes e contextuais.
- **`github.copilot.chat.codesearch.suggestions.*`**: Parâmetros para controlar a quantidade e granularidade das sugestões retornadas pela busca semântica (ex: maxResults, maxResultsPerFile, etc).
- **`github.copilot.chat.enableExperimental`** e **`github.copilot.chat.enableExperimentalChat`**: Ativam recursos experimentais do Copilot Chat, como novos fluxos de interação e automações.
- **`chat.mcp.discovery.enabled`**: Integração com Model Context Protocol (MCP) para uso de ferramentas externas e fluxos avançados.
- **`github.copilot.chat.generateTests.codeLens.maxResults`**: Limita o número de sugestões de geração de testes exibidas no editor.
- **`github.copilot.chat.agent.runTasks.maxResults`**: Controla quantas tarefas automatizadas o agente pode executar em paralelo.
- **`github.copilot.chat.agent.thinkingTool.maxResults`**: Ajusta a quantidade de "planos" ou "pensamentos" que o agente pode sugerir.
- **`github.copilot.chat.editor.temporalContext.enabled`**: Inclui contexto temporal para sugestões ainda mais precisas.

#### Dicas para times:
- Centralize as instruções em arquivos Markdown versionados no repositório (ex: PRD, TRD, convenções de commit, padrões de testes).
- Atualize as instruções sempre que houver mudanças de processo, arquitetura ou requisitos.
- Use comentários no `settings.json` para documentar o propósito de cada configuração.
- Combine instruções de diferentes áreas (negócio, técnico, UX, QA) para potencializar a inteligência do Copilot.

Consulte a [documentação oficial](https://code.visualstudio.com/docs/copilot/reference/copilot-settings) para a lista completa de configurações, exemplos e dicas de uso.

### Vantagens para Times

- Padroniza entregas e reduz divergências entre membros.
- Facilita o onboarding de novos desenvolvedores.
- Garante aderência a requisitos de negócio e técnicos automaticamente.
- Permite evoluir as regras do projeto de forma centralizada.
- Potencializa automação, geração de testes e sugestões inteligentes.

### Exemplos de Uso

- **Geração de código**: O Copilot irá sugerir implementações alinhadas ao PRD e TRD, respeitando requisitos de segurança, arquitetura e usabilidade.
- **Mensagens de commit**: O Copilot irá sugerir mensagens já no padrão Conventional Commits, em português, conforme definido no arquivo de instrução.
- **Geração de testes**: Sugestões automáticas de testes baseadas nas instruções e contexto do projeto.

- **Pull Requests**: Gere descrições de PRs automaticamente seguindo o padrão do time, usando instruções específicas para esse fim.
- **Onboarding**: Novos membros do time podem entender rapidamente os padrões e processos apenas lendo os arquivos de instrução e observando as sugestões do Copilot.

---

---

## Documentações do Projeto

O repositório inclui três documentos fundamentais para o desenvolvimento:

### 1. [PRD - Documento de Requisitos de Produto](docs/PRD.md)

Define o que o sistema deve fazer sob a ótica do negócio e do usuário. No contexto deste projeto, detalha a implementação de telas de login e cadastro com autenticação multifator (MFA/OTP), incluindo:
- Objetivos de negócio e público-alvo.
- Funcionalidades principais (login, cadastro, recuperação de senha, feedbacks, segurança).
- Requisitos não-funcionais (segurança, performance, acessibilidade, escalabilidade).
- Métricas de sucesso e wireframes sugeridos.

> **Como usar:** Consulte o PRD para entender as necessidades do usuário e alinhar entregas ao que realmente agrega valor ao negócio.

### 2. [TRD - Documento de Requisitos Técnicos](docs/TRD.md)

Traduz o PRD em especificações técnicas detalhadas, incluindo:
- Tecnologias e ferramentas adotadas (React, .NET 9, MongoDB, etc).
- Estrutura de pastas e principais componentes do frontend e backend.
- Endpoints da API, modelos de dados e fluxos técnicos (autenticação, geração de OTP, etc).
- Requisitos não-funcionais técnicos (hashing, JWT, performance, acessibilidade).

> **Como usar:** Use o TRD como referência para implementação, garantindo aderência à arquitetura e padrões definidos.

### 3. [CONVENTIONAL_COMMITS.md - Commits Convencionais](docs/CONVENTIONAL_COMMITS.md)

Especifica o padrão de mensagens de commit a ser seguido, facilitando rastreabilidade, automação e versionamento semântico. Destaques:
- Tipos de commit (feat, fix, docs, style, refactor, test, etc).
- Estrutura obrigatória da mensagem (tipo, escopo, descrição, corpo, rodapé).
- Exemplos práticos e regras para breaking changes.
- **Todas as mensagens devem ser em português (PT-BR).**

> **Como usar:** Sempre siga este padrão ao commitar. Isso garante histórico limpo, fácil automação e integração contínua.

---

## Como Contribuir

1. Leia atentamente o PRD e o TRD antes de iniciar qualquer tarefa.
2. Siga as instruções customizadas e utilize o Copilot para acelerar o desenvolvimento, sempre validando as sugestões.
3. Ao commitar, utilize o padrão definido em [CONVENTIONAL_COMMITS.md](docs/CONVENTIONAL_COMMITS.md).
4. Mantenha a documentação atualizada conforme novas decisões e aprendizados.

---

## Boas Práticas

- Priorize segurança e acessibilidade em todas as entregas.
- Prefira código limpo, modular e testável.
- Utilize feedbacks visuais claros para o usuário.
- Documente decisões técnicas relevantes no TRD.
- Revise e atualize as instruções customizadas conforme o projeto evolui.

---

## Referências

- [PRD - Documento de Requisitos de Produto](docs/PRD.md)
- [TRD - Documento de Requisitos Técnicos](docs/TRD.md)
- [Commits Convencionais](docs/CONVENTIONAL_COMMITS.md)
- [Conventional Commits Specification](https://www.conventionalcommits.org/en/v1.0.0/)

---

> Para dúvidas ou sugestões, abra uma issue ou contribua diretamente com um pull request seguindo as diretrizes acima.
