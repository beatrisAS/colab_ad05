<div align="center">

# 🐶🐱 APIs em Python: Cachorros, Gatos e uma Galeria

### Requisições HTTP, dados JSON, downloads de imagens e geração de HTML

Um conjunto progressivo de notebooks para praticar o consumo de APIs públicas no Google Colab — de uma imagem aleatória até uma galeria comparativa que pode ser baixada como arquivo ZIP.

[![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Google Colab](https://img.shields.io/badge/Google%20Colab-notebooks-F9AB00?logo=googlecolab&logoColor=white)](https://colab.research.google.com/)
[![Dog CEO API](https://img.shields.io/badge/API-Dog%20CEO-8A5A44)](https://dog.ceo/dog-api/)
[![The Cat API](https://img.shields.io/badge/API-The%20Cat%20API-6D79A8)](https://thecatapi.com/)
[![HTTP](https://img.shields.io/badge/HTTP-GET-6C63FF)](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Methods/GET)

</div>

---

## 📌 Visão geral

Este repositório reúne quatro notebooks para aprender a consumir APIs com Python e trabalhar com imagens recebidas pela internet. As atividades usam a [Dog CEO API](https://dog.ceo/dog-api/) para imagens de cães e a [The Cat API](https://thecatapi.com/) para imagens de gatos.

A sequência começa com o download de uma imagem de cada animal, avança para várias imagens e termina com a criação de uma galeria HTML de duas colunas, que pode ser visualizada no notebook e baixada em um ZIP.

> **Importante:** as APIs fornecem imagens aleatórias. Executar o notebook novamente pode retornar imagens diferentes. Os arquivos baixados no ambiente temporário do Colab desaparecem quando a sessão é encerrada, a menos que sejam baixados ou copiados para um armazenamento persistente.

---

## 🎯 Objetivos de aprendizagem

Ao percorrer os notebooks, você pratica:

- fazer requisições HTTP GET com `requests`;
- interpretar respostas JSON de APIs;
- localizar URLs de imagens nos campos retornados;
- baixar conteúdo binário e salvar arquivos no disco;
- criar diretórios e montar caminhos com `os`;
- repetir uma operação para vários resultados;
- exibir imagens dentro do Jupyter/Colab;
- produzir um arquivo HTML com CSS simples;
- entender a diferença entre caminhos de arquivo, URLs e imagens incorporadas em Base64;
- compactar arquivos e baixar o ZIP gerado.

---

## 🛠️ Tecnologias e serviços

| Ferramenta ou serviço | Uso nos notebooks |
| --- | --- |
| **Python 3** | Linguagem usada para enviar requisições, processar respostas e gerar arquivos. |
| **Google Colab / Jupyter** | Ambiente para abrir e executar os notebooks. |
| **`requests`** | Envia requisições HTTP e baixa os bytes das imagens. |
| **Dog CEO API** | Retorna URLs de imagens aleatórias de cães. |
| **The Cat API** | Retorna URLs de imagens aleatórias de gatos. |
| **`os`** | Cria diretórios e manipula caminhos e extensões. |
| **`IPython.display`** | Exibe imagens e HTML dentro do notebook. |
| **`base64`** | Codifica imagens para incorporá-las no HTML exibido no Colab. |
| **`zipfile` / `shutil`** | Compacta os arquivos gerados para download. |

Os notebooks foram preparados para o Google Colab, onde `requests` e os módulos padrão do Python usados nas atividades já estão disponíveis. Não há um arquivo `requirements.txt` no repositório.

---

## 📁 Estrutura do repositório

```text
colab_ad05/
│
├── README.md
├── desafio_01.ipynb
├── desafio_02.ipynb
│
└── api/
    ├── cat.ipynb
    └── dog.ipynb
```

| Arquivo | Nível | O que faz |
| --- | --- | --- |
| [`api/cat.ipynb`](api/cat.ipynb) | Inicial | Busca, baixa e exibe uma imagem aleatória de gato. |
| [`api/dog.ipynb`](api/dog.ipynb) | Inicial | Busca, baixa e exibe uma imagem aleatória de cachorro. |
| [`desafio_01.ipynb`](desafio_01.ipynb) | Prática | Pede várias imagens de cães e gatos e salva os arquivos com nomes diferentes. Contém lacunas para completar. |
| [`desafio_02.ipynb`](desafio_02.ipynb) | Projeto final | Baixa imagens, cria uma galeria HTML “Cachorros vs Gatos”, exibe-a no notebook e monta um ZIP. Contém lacunas para completar. |

---

## 📓 Notebooks do repositório

### 1. Uma imagem de gato

[![Abrir `cat.ipynb` no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/beatrisAS/colab_ad05/blob/main/api/cat.ipynb)

O notebook consulta `https://api.thecatapi.com/v1/images/search`, lê a URL da imagem no campo `url`, baixa o conteúdo e salva o arquivo como `imagens/cat/cat.jpg`. Em seguida, exibe a imagem no notebook.

### 2. Uma imagem de cachorro

[![Abrir `dog.ipynb` no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/beatrisAS/colab_ad05/blob/main/api/dog.ipynb)

O notebook consulta `https://dog.ceo/api/breeds/image/random`, lê a URL em `message`, baixa a imagem e salva o arquivo como `imagens/dog/dog.jpg`. Depois, exibe a imagem no notebook.

### 3. Várias imagens

[![Abrir `desafio_01.ipynb` no Colab](https://colab.research.google.com/github/beatrisAS/colab_ad05/blob/main/desafio_01.ipynb)

A atividade define `QUANTIDADE = 5` para baixar cinco imagens de cada tipo. Usa os endpoints de múltiplas imagens das APIs, salva os arquivos com nomes como `dog_1` e `cat_1`, mostra as imagens e oferece a opção de baixar um ZIP.

O notebook contém linhas marcadas para completar antes de executar todas as células.

### 4. Galeria “Cachorros vs Gatos”

[![Abrir `desafio_02.ipynb` no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/beatrisAS/colab_ad05/blob/main/desafio_02.ipynb)

A atividade define `QUANTIDADE = 6` por animal, baixa as imagens e gera `galeria.html`. A página apresenta duas colunas, uma para cachorros e outra para gatos. O notebook também exibe uma versão com imagens incorporadas em Base64 e prepara `galeria.zip` para baixar.

Esse notebook também possui trechos incompletos sinalizados com `___` e comentários `# complete esta linha`.

---

## 🔄 Fluxo de funcionamento

```text
Notebook Python
      │
      │ GET: solicitar imagens aleatórias
      ▼
APIs públicas (Dog CEO / The Cat API)
      │
      │ resposta JSON com uma ou mais URLs
      ▼
Python lê as URLs e baixa os bytes das imagens
      │
      ├── salva arquivos em pastas locais do ambiente
      ├── exibe imagens no notebook
      └── opcionalmente monta galeria HTML e arquivo ZIP
```

### Respostas das APIs usadas

A Dog CEO API retorna um objeto com a URL em `message`, ou uma lista de URLs em `message` quando se usa o endpoint de múltiplas imagens.

A The Cat API retorna uma lista de objetos, cada um com uma URL no campo `url`. O parâmetro `limit` define quantos resultados são solicitados nos notebooks de múltiplas imagens.

O notebook lê essas respostas e depois faz uma **segunda requisição** para baixar cada imagem a partir da URL encontrada.

---

## 🚀 Como executar

### Pré-requisitos

- Uma conta Google com acesso ao Google Colab, ou um ambiente Jupyter com Python 3.
- Acesso à internet para chamar as APIs e baixar as imagens.
- Uma sessão do Colab ativa para executar os notebooks online.

### Opção A — Abrir no Google Colab

1. Escolha o notebook pelos links acima.
2. No Colab, crie uma cópia se quiser manter suas alterações sem editar o original.
3. Conecte a um ambiente de execução.
4. Execute as células **de cima para baixo**, usando o botão de execução ou `Shift + Enter`.
5. Nos notebooks de desafio, complete primeiro as linhas sinalizadas com `___` e `# complete esta linha`.
6. Confira as mensagens de conclusão, as imagens exibidas e os arquivos na área de arquivos do Colab.

### Opção B — Executar em Jupyter local

1. Baixe ou clone o repositório.
2. Abra um terminal na pasta e instale as dependências usadas pelo notebook:

```bash
python -m pip install requests jupyter
```

3. Inicie Jupyter Notebook ou JupyterLab e abra o `.ipynb` desejado.
4. Execute as células na ordem.

Os notebooks usam componentes `IPython.display` para visualização. O bloco de download tenta usar `google.colab.files` quando está no Colab; fora do Colab, o ZIP é apenas criado no diretório atual e deverá ser baixado por outros meios.

> A execução fora do Colab depende da configuração local do Jupyter e das extensões instaladas. O fluxo foi preparado e descrito para o Colab.

---

## ✍️ Desafios com código incompleto

Os arquivos `desafio_01.ipynb` e `desafio_02.ipynb` são atividades para completar. As lacunas são intencionais e fazem parte do exercício; os notebooks não devem ser considerados prontos para execução integral antes de preenchê-las.

### `desafio_01.ipynb`

As células de múltiplas imagens têm linhas com `# complete esta linha`. A atividade envolve:

- pedir `QUANTIDADE` imagens aleatórias de cães;
- percorrer a lista de URLs recebida;
- salvar cada imagem com um nome numerado;
- pedir o limite correspondente de imagens de gatos usando o parâmetro da API;
- guardar e exibir os arquivos.

### `desafio_02.ipynb`

As células de download contêm lacunas no endereço dos endpoints e na extração das URLs. A atividade envolve:

- requisitar uma lista de URLs de cães;
- percorrer as URLs e salvar os arquivos;
- pedir imagens de gatos com um limite;
- extrair a URL de cada objeto retornado;
- gerar uma página HTML para download e uma versão incorporada para exibição.

> Dica de estudo: consulte os notebooks iniciais `api/dog.ipynb` e `api/cat.ipynb` para ver como cada resposta JSON individual é acessada. Depois, compare com as respostas em lote descritas na documentação oficial das APIs.

---

## 📦 Arquivos gerados

Os caminhos abaixo são relativos ao diretório atual do ambiente em que o notebook está rodando.

| Notebook | Saídas principais |
| --- | --- |
| `api/cat.ipynb` | `imagens/cat/cat.jpg` |
| `api/dog.ipynb` | `imagens/dog/dog.jpg` |
| `desafio_01.ipynb` | `imagens/multiplas/`, com imagens nomeadas `dog_1`, `cat_1` etc.; opcionalmente, `multiplas.zip`. |
| `desafio_02.ipynb` | `imagens/galeria/`, `galeria.html` e `galeria.zip`. |

### Sobre o `galeria.html` e o ZIP

No ZIP do desafio 02, o HTML usa caminhos relativos para localizar as imagens em `imagens/galeria/`. Depois de baixar e extrair `galeria.zip`, mantenha o arquivo `galeria.html` junto da pasta `imagens/` e abra o HTML em um navegador.

Para visualização no Colab, a função `embutir` converte as imagens para Base64. Essa versão é montada para ser exibida no notebook porque o iframe de saída não acessa diretamente os arquivos locais da sessão da mesma maneira que o processo Python.

### Persistência dos arquivos

O disco da sessão do Colab é temporário. Para conservar os resultados:

- baixe o arquivo ZIP quando o notebook oferecer essa opção;
- ou use o painel de arquivos do Colab para baixar os itens desejados;
- para armazenamento de longo prazo, copie os resultados para um destino persistente apropriado, com as permissões necessárias.

---

## ⚠️ Cuidados e limitações

- **Resultados aleatórios:** uma nova chamada pode retornar imagens diferentes.
- **Conexão necessária:** as chamadas às APIs e os downloads precisam de acesso à internet.
- **Disponibilidade externa:** os serviços podem impor limites, mudar respostas ou ficar temporariamente indisponíveis.
- **Tratamento de erros:** o código atual não aplica uma validação completa de status HTTP antes de interpretar JSON ou salvar conteúdo. Uma resposta de erro pode resultar em exceção ou arquivo inválido.
- **Extensão de arquivo:** os notebooks de desafio derivam a extensão do caminho da URL e usam `.jpg` como alternativa; a extensão não substitui a validação do formato real do conteúdo.
- **Armazenamento temporário:** arquivos criados no Colab somem ao término da sessão, a menos que sejam baixados ou copiados.
- **Código didático:** os desafios 01 e 02 possuem lacunas intencionais; complete-as antes de executar o fluxo inteiro.
- **Uso das APIs:** consulte as condições, limites e políticas vigentes de cada serviço antes de uso frequente ou em aplicações públicas.

---

## 🧰 Solução de problemas

| Sintoma | O que verificar |
| --- | --- |
| `NameError` ou erro de sintaxe nos desafios | Confira se todos os `___` e trechos `# complete esta linha` foram preenchidos corretamente. |
| Erro ao acessar `data[0]` no notebook de gatos | A resposta pode estar vazia ou em formato de erro. Confira o status da requisição e o conteúdo JSON retornado. |
| Erro ao acessar `data['message']` no notebook de cães | Veja se a API respondeu com sucesso e se o JSON contém `message`. |
| A requisição falha ou demora | Verifique a conexão, tente novamente mais tarde e confira a disponibilidade da API. |
| O arquivo é criado, mas não abre como imagem | Confira se a resposta HTTP foi bem-sucedida e se o conteúdo baixado é realmente uma imagem antes de salvá-lo. |
| Não encontro os arquivos no Colab | Abra o painel de arquivos e procure em `imagens/`; o diretório atual geralmente é `/content`. |
| Perdi as imagens ao fechar a sessão | O ambiente do Colab é temporário. Baixe o ZIP ou os arquivos antes de encerrar a sessão. |
| `google.colab.files` não está disponível | Essa função é específica do Colab. Em outro ambiente, o ZIP é criado no diretório atual e pode ser transferido manualmente. |
| A galeria HTML não mostra imagens depois de extrair o ZIP | Preserve a estrutura relativa: `galeria.html` deve ficar ao lado da pasta `imagens/galeria/`. |

---

## 💡 Possíveis melhorias

Estas ideias são extensões futuras; não estão implementadas nos notebooks atuais:

- adicionar `timeout` e verificar `response.raise_for_status()` antes de processar respostas;
- validar o formato da resposta JSON e a presença dos campos esperados;
- identificar o tipo real do conteúdo por cabeçalho ou assinatura, em vez de confiar apenas na extensão da URL;
- tratar falhas individuais de download sem interromper toda a atividade;
- tornar configurável a quantidade e o diretório de saída;
- oferecer opções por raça, categoria ou outros filtros suportados pelas APIs;
- permitir salvar os arquivos em armazenamento persistente;
- adicionar legendas, layout responsivo, créditos e informações de origem à galeria;
- organizar funções comuns num módulo Python reutilizável;
- acrescentar testes usando respostas simuladas, sem depender da disponibilidade das APIs.

---

## 📚 Referências

- [Dog CEO API — documentação](https://dog.ceo/dog-api/)
- [The Cat API — documentação](https://thecatapi.com/)
- [Biblioteca `requests`](https://requests.readthedocs.io/en/latest/)
- [Requisições GET — MDN em português](https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Methods/GET)
- [Documentação do Python em português](https://docs.python.org/pt-br/3/)
- [Google Colab](https://colab.research.google.com/)
- [Jupyter Notebook](https://jupyter.org/)

---

## 👩‍💻 Autoria

**Beatris Antunes Silva**

[GitHub](https://github.com/beatrisAS) • [LinkedIn](https://www.linkedin.com/in/beatrisantunessilva/)

---

<div align="center">
  Projeto de estudo sobre consumo de APIs e manipulação de arquivos com Python no contexto do bootcamp de Analista de Dados da Generation Brasil.
</div>
