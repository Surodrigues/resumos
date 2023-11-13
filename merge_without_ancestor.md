# Unindo repositórios com origens independentes 

## Descrição  

Passo-a-passo para unir um repositório local a um remoto já existente.

## Passo-a-passo  

1 - na pasta do projeto local, adicionar o repositório remoto¹:
    $ git add origin _URL_REPOSITÓRIO_REMOTO_
2 - buscar as referências do repositório remoto:
    $ git fetch origin
3 - fazer o merge permitindo origens divergentes²:
    $ git merge --allow-unrelated-histories origin/master
    > será solicitado para adicionar uma mensagem ao commit. escreva a mensagem, salve o arquivo e feche.
4 - enviar para o repositório remoto
    $ git push origin master

## Conclusão

Os dois repositórios serão unidos pelo commit gerado no merge. o histórico de commits será mesclado, podendo ser visualizado com git log. ex.: $ git log --graph --oneline --decorate --all  
Importante salientar que não haviam arquivos conflitantes.

## Notas

(¹) Aqui nomeei o repositório remoto com a mesma configuração base: origin
(²) Por padrão, o git não permite o merge de históricos sem um ancestral em comum. A tag --allow-unrelated-histories sobrescreve o padrão.só é útil com merge.

## Referências

- https://git-scm.com/docs/git-merge  
- https://dev.to/donovanrichardson/adding-a-new-remote-and-merging-unrelated-branches-1mkm