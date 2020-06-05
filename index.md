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

Os próximos quadros são os oito "frames" tirados com a câmera no ambiente do blender. Elas foram juntadas em um "grid" 4x2 onde cada imagem do grid representa uma câmera da matriz de câmera. Como foi utilizada uma matriz 8x8, temos um total de 64 imagens por "frame".

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/juntos2.jpg)

Segue abaixo alguns parâmetros da câmera utilizada.

Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 20.0 mm |
Tamanho do sensor(Sensor Size) | 15.0 mm |
F-stop | 100.0 |
Linha Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 10.0 m |
Offset | 3.4 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -3.6 |
Disparidade máxima | -0.7 |

O vídeo abaixo retrata a cena e a possibilidade de alterar o foco do vídeo durante sua realização.


### Return to Home

Para esse projeto intitulado "Return to Home" um vídeo com seis "frames" foi criado. Abaixo coloco três "frames" selecionados que caracterizam a movimentação que ocorre no cenário.

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/CV_MD_1.jpg)

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/CV_MD_3.jpg)

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/CV_MD_6.jpg)

Aqui apresento os 6 "frames" num formato de "grid" 3x2. Novamente, cada "frame" apresenta um total de 64 imagens.

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/juntos.jpg)

Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 100.0 mm |
Tamanho do sensor(Sensor Size) | 50.0 mm |
F-stop | 100.0 |
Linha Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 8.0 m |
Offset | 6.4 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -6.6 |
Disparidade máxima | 1.1 |

Confira abaixo o vídeo criado dessa animação.



### The Airplane

As imagens abaixo se referem ao cenário "The Airplane". Novamente, os "frames" selecionados retratam o movimento de translação do objeto da cena.

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/CV_MD_1.jpg)

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/CV_MD_4.jpg)

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/CV_MD_8.jpg)

Essa animação foi feita com oitro "frames", dessa forma, apresentamos todos eles nesse formato de grid 4x2. 

![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/juntos.jpg)


Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 50.0 mm |
Tamanho do sensor(Sensor Size) | 35.0 mm |
F-stop | 100.0 |
Linha Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 8.0 m |
Offset | 4.57 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -4.7 |
Disparidade máxima | -1.1 |

Segue o vídeo desse projeto abaixo.








