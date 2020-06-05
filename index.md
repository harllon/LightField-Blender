# Exposição de Resultados

Objetivo: Expor os resultados obtidos até agora. Irei apresentar os cenários criados da seguinte forma: Inicialmente irei apresentar três frames selecionados de cada cenário além de seus mapas de disparidade. Esses frames foram selecionadas de forma que possam mostrar da melhor forma o cenário e as movimentações que acontecem nele. Em seguida irei apresentar as imagens em um formato de "grid" 8x8 onde coloco todas as imagens obtidas para cada cenário. Por fim, utilizando um visualizador de lightfield, apresentarei vídeos que mostram as animações criadas.

Algumas observações:
1. Os cenários criados tem elementos de trabalhos de outros, que disponibilizam suas artes no site [sketchfab](https://sketchfab.com/feed). Os créditos serão devidamente colocados
2. Os códigos utilizados serão colocados nesse repositório do github: [LightField-Blender](https://github.com/harllon/LightField-Blender)
3. Todos as imagens foram tiradas utilizando uma simulação de câmera plenóptica feita no blender. Além disso, foi utilizada sempre uma matriz 8x8 de "micro-câmeras"
4. As movimentações realizadas consistem em translações simples de forma que para cada "frame" os valores mínimos e máximos da disparidade no sejam alterados.

## Cenários

### Tower of Gods
A sequência de imagens abaixo são três "frames" do projeto "Tower of Gods". Esses "frames" foram selecionados de forma que a animaço possa ser devidamente retratada.

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/CV_MD_1.jpg)

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/CV_MD_4.jpg)

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/CV_MD_8.jpg)

Os próximos quadros são os oito "frames" tirados com a câmera no ambiente do blender. Elas foram juntadas em um grid onde cada imagem do grid representa uma câmera da matriz de câmera. Como foi utilizada uma matriz 8x8, temos um total de 64 imagens por "frame".

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/juntos2.jpg)

Segue abaixo alguns parâmetros da câmera utilizada.

Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 20.0 mm |
Tamanho do sensor(Sensor Size) | 15.0 mm |
F-stop | 100.0 |
Linha Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 10.0 m |
Offset | 3.4133333333333336 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -3.6 |
Disparidade máxima | -0.7 |

O vídeo abaixo retrata a cena e a possibilidade de alterar o foco do vídeo durante sua realização.


### The Airplane









### Return to Home
