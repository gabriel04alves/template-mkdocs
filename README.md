# Template MkDocs

Um template simples para criar documentações usando MkDocs com tema Material Design e deploy automático no GitHub Pages.

## Como usar este template

### 1. Criar novo repositório

1. Clique em "Use this template" no GitHub
2. Nomeie seu novo repositório
3. Clone o repositório para sua máquina local

### 2. Configuração inicial

Edite o arquivo `mkdocs.yml` e altere as seguintes configurações:

```yaml
site_name: Seu Nome da Documentação # Altere aqui
```

### 3. Instalação local (opcional)

Para testar localmente antes do deploy:

```bash
# Instalar dependências
pip install mkdocs-material

# Servir localmente
mkdocs serve
```

A documentação estará disponível em `http://127.0.0.1:8000`

## Estrutura do projeto

```
template-mkdocs/
├── docs/                 # Arquivos de documentação
│   └── index.md         # Página inicial
├── .github/workflows/   # GitHub Actions
│   └── ci.yml          # Deploy automático
├── mkdocs.yml          # Configuração do MkDocs
└── README.md           # Este arquivo
```

## Criando conteúdo

### Adicionando páginas

1. Crie novos arquivos `.md` na pasta `docs/`
2. Adicione as páginas no `mkdocs.yml`:

```yaml
nav:
  - Início: index.md
  - Sobre: sobre.md
  - Guias: guias.md
```

### Formatação suportada

- **Admonitions**: Caixas de aviso, dica, etc.
- **Syntax highlighting**: Destaque de código
- **Tabs**: Abas para organizar conteúdo
- **Links permanentes**: Para títulos

Exemplo de admonition:

```markdown
!!! note "Nota"
Este é um exemplo de caixa de nota.
```

## Deploy no GitHub Pages

O deploy é **automático**! Sempre que você fizer push para a branch `main`:

1. O GitHub Actions será executado
2. A documentação será construída
3. Os arquivos serão publicados na branch `gh-pages`
4. Sua documentação estará disponível em: `https://seuusuario.github.io/nome-do-repo`

### Ativando o GitHub Pages

1. Vá em Settings → Pages no seu repositório
2. Em "Source", selecione "Deploy from a branch"
3. Escolha a branch `gh-pages`
4. Clique em "Save"

## Personalização

### Cores e tema

Edite o `mkdocs.yml` para personalizar:

```yaml
theme:
  palette:
    - scheme: default
      primary: blue # Mude a cor aqui
```

Cores disponíveis: `red`, `pink`, `purple`, `blue`, `cyan`, `teal`, `green`, `yellow`, `orange`

### Extensões disponíveis

- `admonition`: Caixas de aviso
- `codehilite`: Destaque de sintaxe
- `toc`: Índice automático
- `pymdownx.tabbed`: Abas
- `pymdownx.superfences`: Code blocks avançados

## Dicas

- Use headers (`#`, `##`, `###`) para organizar o conteúdo
- Coloque imagens na pasta `docs/images/`
- Teste localmente com `mkdocs serve` antes de fazer commit
- O deploy leva alguns minutos para aparecer online

## Solução de problemas

**Deploy falhou?**

- Verifique se o `mkdocs.yml` está com sintaxe correta
- Confira se todas as páginas referenciadas no `nav` existem

**Página não carrega?**

- Aguarde alguns minutos após o deploy
- Verifique se o GitHub Pages está ativado nas configurações do repositório

---

Feito usando [MkDocs](https://www.mkdocs.org/) e [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
