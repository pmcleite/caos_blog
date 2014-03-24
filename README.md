# Organização do conteúdo

## Tipos de artigos

Assume-se a existência de dois tipos de artigos:

- Os **posts individuais**, que não têm qualquer relação com qualquer outro post publicado;

- E os posts que pertencem a uma dada **série de posts** (e.g., Algoritmos e Complexidade).

## Estrutura de ficheiros

Cada post terá uma pasta associada, com o nome igual ao nome do título do post, uma vez que poderão existir posts com conteúdo associado para além do ficheiro markdown (como imagens, por exemplo).

Assim, a estrutura sugerida para a organização destes será, para já, a seguinte:

- /singles/ano/mes/nome_post/ *(Para artigos individuais)*

- /series/nome_serie/ano/mes/nome_post/ *(Para artigos de uma determinada série de artigos)*

O ficheiro de Markdown com o texto do artigo deverá ter como nome, naturalmente, **nome_post.md**.

# Publicação de artigos

- Criação de novo branch, a partir do branch *articles*, com o nome:
  -	*iniciaisAutor-titulo* (Individuais)
  -	*iniciaisAutor-serie-titulo* (Série)
- Commit do artigo
- Criação de pull request para merge do branch criado com o branch articles.
- Aguardar por feedback e eventual correcção de erros que possa ter.
- Responsável pelo blog faz merge para o branch articles e publica o artigo.
