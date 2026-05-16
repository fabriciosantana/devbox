# devboxes

Modelos de ambientes de desenvolvimento baseados em Dev Containers.

Este repositório centraliza as configurações que uso para iniciar projetos em
Java, Python/data science e LaTeX. Cada ambiente fica em uma pasta própria com
uma subpasta `.devcontainer` pronta para ser reaproveitada.

## Ambientes

| Ambiente | Pasta | Referência |
| --- | --- | --- |
| Java | `java/.devcontainer` | `fabriciosantana/poo`, branch `2026.1` |
| Python | `python/.devcontainer` | `fabriciosantana/mcdia`, branch `main` |
| LaTeX | `latex/.devcontainer` | `fabriciosantana/latex`, branch `main` |

## Como usar em outro projeto

Copie o modelo desejado para a raiz do projeto:

```bash
cp -R java/.devcontainer /caminho/do/projeto/.devcontainer
```

Depois abra o projeto no VS Code e use o comando:

```text
Dev Containers: Reopen in Container
```

Troque `java` por `python` ou `latex` conforme o ambiente desejado.

## Como testar neste repositório

Abra uma das pastas de ambiente no VS Code, por exemplo `java`, e execute
`Dev Containers: Reopen in Container`. A configuração será lida a partir de
`java/.devcontainer/devcontainer.json`.

## Atualização das referências

As configurações foram copiadas das referências acima para servir como modelos
locais. Quando algum repositório de origem mudar, atualize a pasta correspondente
neste repositório e registre a alteração no histórico do Git.
