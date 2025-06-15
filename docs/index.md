# [Template MkDocs](https://github.com/gabriel04alves/template-mkdocs)

Um template simples para criar documentações usando MkDocs com tema Material Design e deploy automático no GitHub Pages.

## Como usar este template

### 1. Criar novo repositório

1. Clique em "Use this template" no [repositório no GitHub](https://github.com/gabriel04alves/template-mkdocs)
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
# Criar ambiente virtual (recomendado)
python -m venv .venv

# Ativar ambiente virtual
# No Linux/macOS:
source .venv/bin/activate
# No Windows:
# .venv\Scripts\activate

# Instalar dependências
pip install --upgrade pip
pip install -r requirements.txt

# Servir localmente
mkdocs serve
```

A documentação estará disponível em `http://127.0.0.1:8000`

**Nota**: O uso de ambiente virtual é altamente recomendado para evitar conflitos de dependências.

## Estrutura do projeto

```
template-mkdocs/
├── docs/                 # Arquivos de documentação
│   └── index.md         # Página inicial
├── .github/workflows/   # GitHub Actions
│   └── ci.yml          # Deploy automático
├── mkdocs.yml          # Configuração do MkDocs
├── requirements.txt    # Dependências Python
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

Este template inclui diversas extensões para formatação avançada:

#### Extensões Markdown básicas:

- **Admonitions**: Caixas de aviso, dica, erro, etc.
- **Syntax highlighting**: Destaque de código com Pygments
- **Tables**: Tabelas com suporte a alinhamento
- **Footnotes**: Notas de rodapé
- **Abbreviations**: Abreviações com tooltips
- **Definition lists**: Listas de definição

#### Extensões PyMdown:

- **Tabbed**: Abas para organizar conteúdo
- **Details**: Seções recolhíveis
- **Emoji**: Suporte a emojis :smile:
- **Keys**: Representação de teclas ++ctrl+c++
- **Math**: Fórmulas matemáticas com MathJax
- **Task lists**: Listas de tarefas com checkboxes
- **Superfences**: Code blocks avançados com anotações

#### Plugins adicionais:

- **Search**: Busca integrada
- **Git revision date**: Data de criação e modificação dos arquivos

Exemplo de admonition:

```markdown
!!! note "Nota"
Este é um exemplo de caixa de nota.

!!! warning "Atenção"
Cuidado com esta configuração!
```

Exemplo de abas:

```markdown
=== "Python"
`python
    print("Hello World")
    `

=== "JavaScript"
`javascript
    console.log("Hello World");
    `
```

## Deploy no GitHub Pages

O deploy é **automático**! Sempre que você fizer push para a branch `main`:

1. O GitHub Actions será executado
2. A documentação será construída usando ambiente virtual
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
      primary: green # Mude a cor aqui
```

Cores disponíveis: `red`, `pink`, `purple`, `blue`, `cyan`, `teal`, `green`, `yellow`, `orange`

### Extensões disponíveis

O template já vem configurado com as seguintes extensões:

**Markdown Extensions:**

- `abbr`: Abreviações com tooltips
- `admonition`: Caixas de aviso, nota, dica
- `attr_list`: Atributos personalizados para elementos
- `def_list`: Listas de definição
- `footnotes`: Notas de rodapé
- `toc`: Índice automático com links permanentes

**PyMdown Extensions:**

- `pymdownx.arithmatex`: Fórmulas matemáticas
- `pymdownx.betterem`: Melhor formatação de ênfase
- `pymdownx.caret`: Texto sobrescrito
- `pymdownx.details`: Seções recolhíveis
- `pymdownx.emoji`: Suporte a emojis
- `pymdownx.highlight`: Destaque de sintaxe avançado
- `pymdownx.inlinehilite`: Código inline destacado
- `pymdownx.keys`: Representação de teclas
- `pymdownx.magiclink`: Links automáticos
- `pymdownx.mark`: Texto marcado
- `pymdownx.smartsymbols`: Símbolos inteligentes
- `pymdownx.superfences`: Code blocks com anotações
- `pymdownx.tabbed`: Sistema de abas
- `pymdownx.tasklist`: Listas de tarefas
- `pymdownx.tilde`: Texto subscrito e riscado

**Plugins:**

- `search`: Busca integrada na documentação
- `git-revision-date-localized`: Datas de criação e modificação automáticas

## Dicas

- Use headers (`#`, `##`, `###`) para organizar o conteúdo
- Coloque imagens na pasta `docs/images/`
- Use ambiente virtual para desenvolvimento local
- Teste localmente com `mkdocs serve` antes de fazer commit
- O deploy leva alguns minutos para aparecer online
- As datas de criação/modificação são adicionadas automaticamente

## Solução de problemas

**Deploy falhou?**

- Verifique se o `mkdocs.yml` está com sintaxe correta
- Confira se todas as páginas referenciadas no `nav` existem
- Verifique se o `requirements.txt` tem todas as dependências

**Página não carrega?**

- Aguarde alguns minutos após o deploy
- Verifique se o GitHub Pages está ativado nas configurações do repositório

**Problemas com ambiente virtual?**

- Certifique-se de ativar o ambiente virtual antes de instalar dependências
- Use `pip install --upgrade pip` para atualizar o pip
- No Windows, use `python -m pip` se houver problemas com `pip`

**Extensões não funcionam?**

- Verifique se todas as dependências estão instaladas
- Confirme se a extensão está listada no `mkdocs.yml`

---

Feito usando [MkDocs](https://www.mkdocs.org/) e [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
