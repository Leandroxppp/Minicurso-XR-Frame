# Minicurso XR com A-Frame — Aula 1

Exercícios da Aula 1 do minicurso de Realidade Estendida com A-Frame
(UFAL, Instituto de Computação).

## Como rodar
Abra qualquer arquivo da pasta `aula1/` no Chrome com dois cliques.
Os modelos 3D vêm de links Raw do GitHub, então é preciso internet.

## 1. Cena padrão
Código do exemplo da documentação do A-Frame 1.8.0.

![Cena padrão](aula1/img/01-cena-padrao.png)

## 2. Modelo GLB
Usei dois modelos do repositório glTF-Sample-Models: o pato (Duck) e o
abacate (Avocado), sempre pelo link Raw da pasta `glTF-Binary`.
O pato usa `scale="0.5 0.5 0.5"`. O abacate é bem menor no arquivo,
então usei `scale="10 10 10"`.

![Pato](aula1/img/02-modelo-glb-pato.png)
![Abacate](aula1/img/02b-modelo-glb-abacate.png)

## 3. Inspetor
Abri o inspetor com Ctrl + Alt + I e testei `position`, `rotation` e
`scale` no pato. O valor que deixou o pato de frente foi
`rotation="0 -90 0"`. Também testei `scale="1 1 1"` e `position` com
X igual a 1. Como o inspetor não salva no código, passei os valores
escolhidos para o HTML.

![Inspetor](aula1/img/03-inspetor.png)

## 4. Hierarquia
Montei uma mesa (pai) com tampo, quatro pernas e uma bola (filhos).
- Ao mexer no pai, a bola e as pernas se moveram junto.
- Ao mexer só em um filho, apenas ele se moveu.
- Com o pai em `0 0 -3` e a bola em `0 0.875 0`, a bola fica no mundo
  em `0 0.875 -3`, porque a posição do filho é medida a partir do pai.

![Hierarquia](aula1/img/04-hierarquia.png)

## 5. Desafio: mesa com dois modelos
Mesa como entidade pai, com pato e abacate como filhos em cima do
tampo, cenário de fim de tarde (céu laranja, luz ambient e luz
directional).
- O pato precisou de `rotation="0 -90 0"` para ficar de frente.
- Ao adicionar luzes próprias, o A-Frame desliga as luzes padrão, por
  isso a cena ficou alaranjada e mais escura.

![Desafio](aula1/img/05-desafio-mesa.png)

## Dificuldades e aprendizados
- (escreva aqui com suas palavras)

## Referências
- https://aframe.io/docs/1.8.0
- https://github.com/KhronosGroupArchives/glTF-Sample-Models
- Materiais da aula: https://github.com/liliangisellyps/minicurso-xr-aframe
