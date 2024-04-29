# Testes de Desempenho com K6

Este repositório contém scripts simples de teste de desempenho desenvolvido com K6 e uma GitHub Actions para execução contínua dos testes.

## Conteúdo

- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Execução dos Testes](#execução-dos-testes)
- [GitHub Actions](#github-actions)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Requisitos

Antes de executar os testes, certifique-se de ter o [K6](https://k6.io) instalado em seu sistema.
Para instalar o K6, siga as instruções fornecidas na [documentação oficial](https://k6.io/docs/get-started/installation/).

## Instalação

1. Clone este repositório em sua máquina local:

```bash
git clone https://github.com/charlyautomatiza/k6-starter.git
```

2. Navegue até o diretório do projeto:

```bash
cd k6-starter
```

## Execução dos Testes

Para realizar uma execução local, basta executar o seguinte comando:

```bash
k6 run ./src/thresholds.js
```

Para podermos usar o K6 WebDashboard, devemos adicionar a variável de ambiente K6_WEB_DASHBOARD=true, antes do comando de execução

```bash
K6_WEB_DASHBOARD=true k6 run ./src/thresholds.js
```

Para salvar o relatório como um arquivo HTML, podemos executar o seguinte comando

```bash
K6_WEB_DASHBOARD=true K6_WEB_DASHBOARD_EXPORT=html-report.html k6 run ./src/thresholds.js
```

Para executar um teste de navegador, podemos executar o seguinte comando:

```bash
K6_BROWSER_HEADLESS=true k6 run ./src/browser.js
```

Observe que a variável de ambiente `K6_BROWSER_HEADLESS` deve ser definida como `true` para ser executada em ferramentas de integração contínua. Para execução local e depuração, é útil usar a variável com o valor definido como `false` para executar o navegador em primeiro plano.

```bash
K6_BROWSER_HEADLESS=false k6 run ./src/browser.js
```

## GitHub Actions

Este repositório inclui uma GitHub Actions configurada para executar os testes de desempenho continuamente sempre que houver um push para o branch principal. A ação está definida no arquivo [k6-runner.yml](.github/workflows/k6-runner.yml).

## Contribuição

Contribuições são bem-vindas! Se desejar melhorar este projeto, abra uma issue para discutir as alterações propostas.

## Licença

Este projeto está sob a licença Creative Commons CC0 1.0 Universal.
