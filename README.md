# devboxes

Modelos de ambientes de desenvolvimento baseados em Dev Containers.

Este repositório centraliza as configurações que uso para iniciar projetos em
Java, Python/data science e LaTeX. Cada ambiente fica em uma subpasta de
`.devcontainer`, seguindo o formato reconhecido pelo GitHub Codespaces para
múltiplas configurações.

## Ambientes

| Ambiente | Pasta | Referência |
| --- | --- | --- |
| Java | `.devcontainer/java` | `fabriciosantana/poo`, branch `2026.1` |
| Python | `.devcontainer/python` | `fabriciosantana/mcdia`, branch `main` |
| LaTeX | `.devcontainer/latex` | `fabriciosantana/latex`, branch `main` |

## Como usar no Codespaces

Ao criar um Codespace a partir deste repositório, escolha a configuração desejada
em `New with options...`. O Codespaces reconhece os arquivos no padrão:

```text
.devcontainer/<ambiente>/devcontainer.json
```

## Como usar em outro projeto

Copie o modelo desejado para a raiz do projeto:

```bash
cp -R .devcontainer/java /caminho/do/projeto/.devcontainer
```

Depois abra o projeto no VS Code e use o comando:

```text
Dev Containers: Reopen in Container
```

Troque `java` por `python` ou `latex` conforme o ambiente desejado. Ao copiar
para outro projeto, se houver `postCreateCommand`, ajuste o caminho para apontar
para `.devcontainer/post-create.sh`.

## Como testar neste repositório

Crie um Codespace usando `New with options...` ou, no VS Code, selecione a
configuração desejada ao abrir o repositório em container.

## Atualização das referências

As configurações foram copiadas das referências acima para servir como modelos
locais. Quando algum repositório de origem mudar, atualize a pasta correspondente
neste repositório e registre a alteração no histórico do Git.
