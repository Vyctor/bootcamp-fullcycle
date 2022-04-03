# Docker

# Pilares do Aprendizado

- Conceitos básicos do docker
- Criar e manipular contâineres e imagens
- Docker Compose

## Container

É um padrão de unidade de software que empacota código e todas as dependências de uma aplicação fazendo que a mesma seja executada rapidamente de forma confiável de um ambiente computacional para outro. São **processos isolados em execução**

### Como funcionam os containers?

São conjuntos de processos operando isoladamente em um determinado namespace.

- Namespace → Isolam os processos
- C-groups → Isola os recursos computacionais
- Filesystem → Overlay file system, o container executa em cima do sistema operacional, assim o tamanho da imagem é reduzido.

## Imagens

É o agrupamento de várias dependências em camadas.

O estado da imagem é imutável, ao matar o container, tudo se destrói.

As imagens ficam armazenadas no Docker Registry, um repositório de imagens.

## Dockerfile

Arquivo de configuração do Docker, é um arquivo declarativo para a construção de imagens.

Toda vez que o Dockerfile é executado é gerado uma build que resulta em uma nova imagem.