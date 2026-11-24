# Minicurso XR com A-Frame — Aula 1

Exercícios da Aula 1 do minicurso de Realidade Estendida com A-Frame
(UFAL, Instituto de Computação), feitos com A-Frame 1.8.0.

## Como rodar

Abra qualquer arquivo da pasta [`aula1/`](aula1/) no Chrome com dois cliques.
Os modelos 3D são carregados por links Raw do GitHub, então é preciso internet.

## Estrutura

| Arquivo | O que é |
|---|---|
| `01-cena-padrao.html` | Exemplo da documentação (caixa, esfera, cilindro) |
| `02-modelo-glb.html` | Modelo GLB do pato (Duck), usado também no inspetor |
| `02b-modelo-glb-abacate.html` | Modelo GLB do abacate (Avocado) |
| `04-hierarquia.html` | Mesa (pai) com tampo, pernas e bola (filhos) |
| `05-desafio-mesa.html` | Desafio: mesa com dois modelos e luz de fim de tarde |

## 1. Cena padrão

Copiei o código de *Getting Started* da documentação do A-Frame e abri no
navegador. Na cena, arrastar o mouse olha em volta e W A S D anda.

![Cena padrão](aula1/img/01-cena-padrao.png)

## 2. Modelo GLB

Usei dois modelos do repositório
[glTF-Sample-Models](https://github.com/KhronosGroupArchives/glTF-Sample-Models):
o pato (Duck) e o abacate (Avocado), sempre pelo link **Raw** do arquivo `.glb`
da pasta `glTF-Binary`.

São três tags: `a-assets` (carrega os arquivos), `a-asset-item` (dá um `id` e
o `src`) e `a-entity gltf-model="#id"` (coloca o modelo na cena).

Cada modelo vem em um tamanho. O pato usou `scale="0.5 0.5 0.5"`; o abacate é
bem menor no arquivo (cerca de 6 cm), então usei `scale="10 10 10"`.

![Pato](aula1/img/02-modelo-glb-pato.png)
![Abacate](aula1/img/02b-modelo-glb-abacate.png)

## 3. Inspetor

Abri o inspetor com `Ctrl + Alt + I` e testei `position`, `rotation` e `scale`
no pato. O valor que deixou o pato de frente para a câmera foi
`rotation="0 -90 0"`. Também deixei o `scale` em `1 1 1` e movi o pato de 0
para 1 no eixo X.

O inspetor **não salva no código**: ao apertar F5 tudo volta ao original.
Por isso passei os valores escolhidos para o HTML:

```html
<a-entity gltf-model="#pato" position="1 0 -3" rotation="0 -90 0" scale="1 1 1"></a-entity>
```

![Inspetor](aula1/img/03-inspetor.png)

## 4. Hierarquia

Montei uma mesa como entidade pai, com o tampo, quatro pernas e uma bola como
filhos, e fiz três testes:

- Ao mexer no **pai**, a bola e as pernas se moveram junto.
- Ao mexer só em **um filho**, apenas ele se moveu.
- Com o pai em `0 0 -3` e a bola em `0 0.875 0`, a bola fica no mundo em
  `0 0.875 -3`, porque a posição do filho é medida a partir do pai.

![Hierarquia](aula1/img/04-hierarquia.png)

## 5. Desafio: mesa com dois modelos

Passos feitos, cada um continuando a cena do anterior:

1. Mesa como `a-entity` pai, com o tampo e as quatro pernas como filhos (`a-box`).
2. Mudei `position` e `scale` do pai: `position="0 0 -2.5"` e `scale="1.2 1.2 1.2"`.
3. Pato em cima do tampo, como filho da mesa (`scale="0.1 0.1 0.1"`, ~15 cm).
4. Abacate ao lado, com o mesmo tamanho aparente (`scale="2.5 2.5 2.5"`).
5. Usei o inspetor para achar a rotação: o pato precisou de `rotation="0 -90 0"`
   e o abacate já estava de frente.
6. Fim de tarde: céu `#F4A261`, uma luz `ambient` e uma `directional`.

Ao adicionar luzes próprias, o A-Frame desliga as luzes padrão. Por isso a cena
ficou alaranjada e mais escura, como esperado.

![Desafio](aula1/img/05-desafio-mesa.png)

## Dificuldades e aprendizados

- **Link do modelo:** no abacate, coloquei no `src` o endereço da página do
  repositório no GitHub, e a cena ficou vazia. O `src` precisa apontar para o
  arquivo `.glb` em si, pelo botão **Raw**, começando com
  `https://raw.githubusercontent.com/...`.
- **Inspetor x código:** o inspetor é ótimo para testar valores na hora, mas não
  salva nada. Aprendi a anotar o que funcionou e copiar para o HTML.
- **Pai e filho:** mexer no pai move todos os filhos, e a posição de cada filho
  é relativa ao pai. Isso facilita montar objetos compostos, como a mesa.
- **Organização dos arquivos:** ao trocar o link dentro do mesmo arquivo, perdi o
  código do pato. Passei a criar um arquivo novo para cada exercício.

## Referências

- [Documentação do A-Frame 1.8.0](https://aframe.io/docs/1.8.0/)
- [glTF Sample Models (Khronos)](https://github.com/KhronosGroupArchives/glTF-Sample-Models)
- [Repositório da aula](https://github.com/liliangisellyps/minicurso-xr-aframe)
- [Slides da aula](https://liliangisellyps.github.io/minicurso-xr-aframe/slides/)
- [Exercícios da Aula 1](https://liliangisellyps.github.io/minicurso-xr-aframe/aula1/)
