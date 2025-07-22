
# Pokédex Kanto

## Descrição do Projeto

A **Pokédex Kanto** é uma aplicação web interativa que simula a Pokédex da região de Kanto, inspirada nos jogos *Pokémon FireRed* e *Pokémon LeafGreen*.  
O projeto permite consultar informações detalhadas sobre os 151 Pokémon da primeira geração.

A aplicação foi desenvolvida com:

- **Backend** em Python usando **Flask**
- **Frontend** em HTML, CSS e JavaScript
- **Base de dados** em JSON (`pokedex.json`), contendo:  
  número, nome, tipos, descrição, imagens, localização e fraquezas de cada Pokémon.

O sistema inclui:

- Listagem completa dos Pokémon em grade
- Filtro dinâmico por nome, número e tipo (via JavaScript)
- Página de detalhes de cada Pokémon, com informações específicas
- Navegação cíclica entre Pokémon (do 151º retorna para o 1º e vice-versa)

> **Observação:** Este projeto é de caráter educativo. As imagens e dados utilizados pertencem à Nintendo/Game Freak.

---

## Equipe de Desenvolvimento

| Nome | Email |
|---|---|
| José Carlos Pereira Dantas | carlosjose.dantas@aluno.uece.br |
| Antonio Gabriel Amaro De Assis | gabriel.amaro@aluno.uece.br |

---

## Estrutura de Pastas

```
├── static/
│   ├── images/
│   │   ├── 001.png até 151.png           # Sprites pequenas dos Pokémon
│   │   └── bulbasaur.png até mew.png     # Imagens grandes dos Pokémon
│   ├── icon.png                          # Ícone do site
│   ├── pokeicon.png                      # Ícone da Pokédex (cabeçalho)
│   ├── pokeicondetail.png                # Ícone da página de detalhes
│   └── style.css                         # Arquivo de estilos CSS
├── templates/
│   ├── pokedex.html                      # Página principal da Pokédex
│   └── pokemon.html                      # Página de detalhes do Pokémon
├── app.py                                # Backend (Flask)
└── pokedex.json                         # Base de dados dos Pokémon
```

---

## Funcionalidades

### Página Inicial - Pokédex

- Listagem dos Pokémon de **001 a 151**
- Filtro dinâmico (JavaScript) por:
  - Nome
  - Número
  - Tipo
- Link para a página de detalhes de cada Pokémon

### Página de Detalhes - Pokémon

- Exibe:
  - Imagem maior do Pokémon
  - Nome, tipo(s), fraquezas, descrição e localização no jogo original
- Botões para navegar entre o Pokémon anterior e o próximo (com navegação cíclica)

### Busca

- Campo de busca direta por nome ou número
- Se houver correspondência exata, redireciona para a página de detalhes

---

## Arquivos Principais

### `app.py`

- Backend com **Flask**  
- Rotas principais:
  - `/` → Exibe a lista da Pokédex (`pokedex.html`)
  - `/search` → Busca por nome ou número e redireciona para a página de detalhes
  - `/pokemon/<int:number>` → Exibe detalhes do Pokémon (`pokemon.html`)
- Função `load_pokedex()` carrega os dados do `pokedex.json`

### `pokedex.json`

- Base de dados dos Pokémon
- Campos:
  - `number`: Número na Pokédex
  - `name`: Nome do Pokémon
  - `type`, `type1`, `type2`: Tipos primário e secundário (se houver)
  - `description`: Descrição do Pokémon
  - `image`: Sprite pequena para listagem
  - `real`: Imagem maior para página de detalhes
  - `locate`: Localização de captura
  - `weakness`: Fraquezas

### `pokedex.html`

- Página inicial da Pokédex com filtros dinâmicos via JavaScript
- Carregamento de dados com **Jinja2**

### `pokemon.html`

- Página de detalhes do Pokémon selecionado
- Links para Pokémon anterior, próximo e retorno à Pokédex

### `style.css`

- Estilos e aparência da Pokédex

---

## Tecnologias Utilizadas

- **HTML5** – Estrutura das páginas
- **CSS3** – Estilização e layout
- **JavaScript** – Filtros e interatividade no frontend
- **Python 3** – Backend
- **Flask** – Framework web
- **Jinja2** – Templates HTML dinâmicos
- **JSON** – Base de dados dos Pokémon

---

## Como Rodar o Projeto

### 1. Instalar o Python

Certifique-se de ter o **Python 3** ou superior instalado:

```bash
python --version
```

Se necessário, baixe o Python em: [https://www.python.org/downloads/](https://www.python.org/downloads/)

---

### 2. Instalar o Flask

No terminal, execute:

```bash
pip install flask
```

---

### 3. Executar o Projeto

Navegue até a pasta do projeto:

```bash
cd caminho/para/sua/pasta/do/projeto
```

Execute o backend:

```bash
python app.py
```

O servidor Flask iniciará em modo debug na porta **5000**.

---

### 4. Acessar no Navegador

Abra seu navegador e acesse:

```
http://127.0.0.1:5000/
```

Você verá a Pokédex funcionando localmente.

---

## Licença

Projeto com fins didáticos e educativos.  
Todos os direitos sobre personagens e imagens pertencem à **Nintendo** e **Game Freak**.
