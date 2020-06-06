# Projeto de Datasets de LightFields Sintéticos

## Conceitos

### LightField

LightFields são uma função vetorial que descreve a quantidade de luz que atravessa o espaço em todos os pontos e em todas as direções. O espaço de todas as possibilidades de raios de luz é dado pela função plenóptica 5D [1]. Ou seja, a função plenóptica é a representação matemática de um lightfield. No entanto, cabe aqui ressaltar que a função plenóptica, na verdade, é uma função 7D que modela um ambiente 3D dinâmico gravando os raios de luz em qualquer local (x,y,z) sob qualquer direção (𝜃, 𝜑), com qualquer faixa de comprimento de onda (𝜆) e a qualquer instante de tempo (t).[2]


| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/geral/baby_lightfield.jpg) | 
|:--:| 
| *Figura 1: Representação 7D da Função Plenóptica.[2]* |

No entanto, devido a algumas redundâncias na aquisição de informação, podemos utilizar a representaço 5D da função plenóptica e, em alguns casos, a representação 4D que é gerada a partir da parametrização proposta por Marc Levoy e Pat Hanrahan chamada de light slab.[3]

### Câmera Plenóptica

A câmera plenóptica é responsável pela criação de imagens de campo de luz a partir de cenas reais. Essa câmera captura informação sobre o campo de luz emanado da cena, ou seja, intensidade da luz e direção que o raio de luz está viajando no espaço. 
A principal câmera plenóptica, que se tornou referências para diversos trabalhos é a câmera da Lytro. 

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/geral/lytro_cam.jpg) | 
|:--:| 
| *Figura 2: Câmera Plenóptica Lytro[4]* |

A câmera plenóptica da Lytro que detém algumas particularidades. Tal câmera apresenta uma lente principal e um vetor de microlentes posteriores, todas elas captando diferentes raios de luz, como ilustra a figura a segur:

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/geral/plenoptica_cam.png) | 
|:--:| 
| *Figura 3: Esquema interno de uma Câmera Plenóptica.[5]* |

Essa estrutura permite que a imagem gerada possa ser visualizada sob diferentes pontos de vista sem que tenha perda de qualidade ou deformação da imagem. Além disso, há a possibilidade de mudança de foco ao longo da figura após a imagem ser tirada.

### Calibração de Câmera

A calibração de câmera consiste no processo de determinar dados geométricos e ópticos da câmera. Para isso, faz-se necessário o entendimento dos parâmetros da câmera. Tais parâmetros são dividos em dois grupos: Intrínsecos e Extrínsecos 

#### Intrínsecos

Os parâmetros intrínsecos servem para se poder relacionar as coordenadas pixel relativas às imagens com as coordenadas de pontos do espaço medidos no sistema referencial com origem no centro da câmara. Estes parâmetros dependem exclusivamente das características físicas da câmara (da sua geometria interna, do tipo de lente). [6]
A seguir, vamos tratar de alguns parâmetros intrínsecos da câmera que serão mencionados futuramente.

1. Comprimento Focal(Focal Length): É a distância do plano focal (onde está o sensor da câmera) até a retaguarda da lente, quando focada no infinito. Esta é uma propriedade da lente, que determina o ângulo de visão e a perspectiva.[7]. Basicamente, esse parâmetro tem influência direta no quanto a imagem é aparentemente ampliada.

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/geral/macro-focusing-distance-eng.jpg) | 
|:--:| 
| *Figura 4: Exemplificação de distância focal e comprimento focal.[7]* |

2. Tamanho do Sensor(Sensor Size): O tamanho do sensor de uma câmera determina quanta luz ela capta para criar uma imagem. Em outras palavras, os sensores de imagem consistem em milhões de pontos sensíveis à luz, que são usados para registrar informações sobre o que é visto através da lente. Logo, quanto maior esse parâmetro mais luz pode ser captada pela câmera.[8]

3. F-stop: É um parâmetro de câmera que especifica a abertura da lente. É obtida como a razão entre o comprimento focal da lente e o diâmetro da abertura da lente.[9]

#### Extrínsecos

Os parâmetros extrínsecos fornecem informações da posição e orientação da câmera em relação a um certo sistema de coordenadas.
A seguir, vamos tratar de alguns parâmetros extrínsecos da câmera que serão mencionados futuramente.

1. Distância Focal(Focus Distance): É a distância do plano focal até o objeto que está sendo fotografado.[7]

2. Linha Base(Baseline): Utilizado num sistema de câmeras ou micro-lentes. Consiste na distância entre cada uma das câmeras do sistema montado. Tem influência direta na obtenção da disparidade e profundidade de uma imagem.

3. Deslocamento(Offset): É uma medida que indica o quão deslocada do ponto objeto a câmera está.

### Mapa de Disparidade

A disparidade (que pode ser horizontal ou vertical), em linhas gerais, consiste na medida da localização de dois pontos (pixels) homólogos em duas vistas diferentes [10]. Quanto maior for a diferença, maior é o valor de disparidade e menor é o valor da profundidade deste ponto, que vai estar mais perto do observador/câmera. A ideia de disparidade pode ser facilmente verificada quando olhamos para um ponto e fechamos os olhos alternadamente. Notamos que os objetos mais próximos de nós parecem se mover uma distância maior do que os objetos mais distantes. A essa diferença de posição damos o nome de disparidade.


### Blender

o Blender é uma software de criação 3D, com scripts em python. Ela permite a modelagem de ambientes, cenários, objetos, além de criação de animações. [11] É um software voltado para designer que, em seu ambiente, permite a implementação de câmeras virtuais que simulam uma câmera plenóptica e, podem ser utilizadas para a captura de campos de luz sintéticos.

### Datasets 

Nessa seção irei apresentar os cenários criados da seguinte forma: Inicialmente irei apresentar três frames selecionados de cada cenário além de seus mapas de disparidade. Esses frames foram selecionadas de forma que possam mostrar da melhor forma o cenário e as movimentações que acontecem nele. Em seguida irei apresentar as imagens em um formato de "grid" onde coloco todas as imagens obtidas para cada cenário. Por fim, utilizando um visualizador de lightfield, apresentarei vídeos que mostram as animações criadas.

##### Algumas observações:
1. Os cenários criados tem elementos de trabalhos de outros, que disponibilizam suas artes no site [sketchfab]. Os créditos serão devidamente apresentados após cada sequência de imagem.
2. Os códigos utilizados serão colocados nesse repositório do github: [LightField-Blender](https://github.com/harllon/LightField-Blender)
3. Todos as imagens foram tiradas utilizando uma simulação de câmera plenóptica feita no blender[13]. Além disso, foi utilizada sempre uma matriz 8x8 de "micro-câmeras"
4. Esse trabalho foi inspirado no trabalho ["A Dataset and Evaluation Methodology for Depth Estimation on 4D Light Fields"](https://lightfield-analysis.uni-konstanz.de/). Eles disponibilizaram scripts em python que foram utilizados nesse projeto e seu acesso será disponibilizado nas referências[14], [15].
5. O visualizador utilizado pertence ao projeto ["Light Field Video Capture Using a Learning-Based Hybrid Imaging System"](http://cseweb.ucsd.edu/~viscomp/projects/LF/papers/SIG17/lfv/).
6. Os mapas de disparidade foram gerados usando o MatLab.[18]

## Cenários

### Tower of Gods

A sequência de imagens abaixo são três "frames" do projeto "Tower of Gods". Esses "frames" foram selecionados de forma que a animaço possa ser devidamente retratada.

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/CV_MD_1.jpg) | 
|:--:| 
| *Figura 5: Visão Central e sua Disparidade - Frame 0001* |

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/CV_MD_4.jpg) | 
|:--:| 
| *Figura 6: Visão Central e sua Disparidade - Frame 0004* |

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/CV_MD_8.jpg) | 
|:--:| 
| *Figura 7: Visão Central e sua Disparidade - Frame 0008* |

Os próximos quadros são os oito "frames" tirados com a câmera no ambiente do blender. Elas foram juntadas em um "grid" 4x2 onde cada imagem do grid representa uma câmera da matriz de câmera. Como foi utilizada uma matriz 8x8, temos um total de 64 imagens por "frame".

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Tower%20of%20Gods/disparity_colour/juntos2.jpg) | 
|:--:| 
| *Figura 8: LightField - Todos os "frames"* |

Segue abaixo alguns parâmetros da câmera utilizada.

Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 20.0 mm |
Tamanho do sensor(Sensor Size) | 15.0 mm |
F-stop | 100.0 |
Linha de Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 10.0 m |
Deslocamento(Offset) | 3.4 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -3.6 |
Disparidade máxima | -0.7 |

O vídeo abaixo retrata a cena e a possibilidade de alterar o foco do vídeo durante sua realização.




##### Créditos
Domínio de lucidvoo, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Retirada de elementos e junção com outros modelos 3D.
(https://sketchfab.com/3d-models/homework-53-submarine-0d6b1a6a521146e3a65d9835e09514e55)

Domínio de gfon296, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Junção com outros modelos 3D.
https://sketchfab.com/3d-models/nurnberg-91dedd2d5acd4e2c8cfae46cbc0c339b

Domínio de Troublesome, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Alteração nas texturas, coloração, efeitos de cenário e junção com outros modelos 3D.
https://sketchfab.com/3d-models/lighthouse-3a479e4262384bbb95ff4058565fa6ea

### Return to Home

Para esse projeto intitulado "Return to Home" um vídeo com seis "frames" foi criado. Abaixo coloco três "frames" selecionados que caracterizam a movimentação que ocorre no cenário.

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/CV_MD_1.jpg) | 
|:--:| 
| *Figura 9: Visão Central e sua Disparidade - Frame 0001"* |


| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/CV_MD_3.jpg) | 
|:--:| 
| *Figura 10: Visão Central e sua Disparidade - Frame 0003"* |


| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/CV_MD_6.jpg) | 
|:--:| 
| *Figura 11: Visão Central e sua Disparidade - Frame 0006"* |

Aqui apresento os 6 "frames" num formato de "grid" 3x2. Novamente, cada "frame" apresenta um total de 64 imagens.


| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/Return%20to%20Home/disparity_colour/juntos.jpg) | 
|:--:| 
| *Figura 12: LightField - Todos os "frames"* |

Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 100.0 mm |
Tamanho do sensor(Sensor Size) | 50.0 mm |
F-stop | 100.0 |
Linha de Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 8.0 m |
Deslocamento(Offset) | 6.4 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -6.6 |
Disparidade máxima | 1.1 |

Confira abaixo o vídeo criado dessa animação.


##### Créditos
Domínio de KattyLi, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Junção com outros modelos 3D.
https://sketchfab.com/3d-models/whale-house-cb79b20b5533474ba918ce6b93201b3e

Domínio de lucidvoo, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Retirada de elementos e junção com outros modelos 3D.
https://sketchfab.com/3d-models/homework-53-submarine-0d6b1a6a521146e3a65d9835e09514e5

Domínio de Euvand, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Alterações na textura, coloração do modelo e junção com outros modelos 3D.
https://sketchfab.com/3d-models/nortensky-ba544d323fb549f8a27087b612ffbd9c

### The Airplane

As imagens abaixo se referem ao cenário "The Airplane". Novamente, os "frames" selecionados retratam o movimento de translação do objeto da cena.

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/CV_MD_1.jpg) | 
|:--:| 
| *Figura 13: Visão Central e sua Disparidade - Frame 0001"* |

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/CV_MD_4.jpg) | 
|:--:| 
| *Figura 14: Visão Central e sua Disparidade - Frame 0004"* |

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/CV_MD_8.jpg) | 
|:--:| 
| *Figura 15: Visão Central e sua Disparidade - Frame 0008"* |

Essa animação foi feita com oito "frames", dessa forma, apresentamos todos eles nesse formato de "grid" 4x2. 

| ![](https://raw.githubusercontent.com/harllon/LightField-Blender/master/images/The%20Airplane/disparity_colour/juntos.jpg) | 
|:--:| 
| *Figura 16: LightField - Todos os "frames"* |


Parâmetros | Valores
------------ | -------------
Comprimento focal(Focus Length) | 50.0 mm |
Tamanho do sensor(Sensor Size) | 35.0 mm |
F-stop | 100.0 |
Linha de Base(Baseline) | 50.0 mm |
Distância Focal(Focus Distance) | 8.0 m |
Deslocamento(Offset) | 4.57 |
Resolução (x) | 512 px |
Resolução (y) | 352 px |
Disparidade mínima | -4.7 |
Disparidade máxima | -1.1 |

Segue o vídeo desse projeto abaixo.






##### Créditos
Domínio de Akhikyan, 2020, publicado na plataforma https://sketchfab.com/
Todos os direitos reservados. Este modelo 3D não pode ser reproduzido ou usado de forma alguma sem seguir as normas da licença CC Attribution. Segundo esta licença, este modelo 3D foi parcialmente modificado a fim de ser empregado no trabalho de LightFields desenvolvido por Harllon Oliveira da Paz. Para isso, foram feitas as seguintes alterações: Alterações na textura e coloração do modelo.
https://sketchfab.com/3d-models/steampunk-lighthouse-21ac51ebc4874fd08cc74ff75aed328d


## Referências

1. Adelson, E.H., Bergen, J.R., ‘‘The Plenoptic Function and the Elements of Early Vision,’’ In Computation Models of Visual Processing, M. Landy and J.A. Movshon, eds., MIT Press, Cambridge, 1991.
2. Cha Zhang e Tsuhan Chen, “Light Field Sampling”.
3. Marc Levoy and Pat Hanrahan. 1996. Light field rendering. In Proceedings of the 23rd annual conference on Computer graphics and interactive techniques (SIGGRAPH '96). ACM, New York, NY, USA, 31-42.
4. [Lytro LightField Camera-Review](https://www.wired.com/2012/02/lytro-camera-2/)
5. Wanner, Sven & Keuper (Fehr), Janis & Jähne, Bernd. (2011). Generating EPI Representations of 4D Light Fields with a Single Lens Focused Plenoptic Camera. 6938. 90-101. 10.1007/978-3-642-24028-7_9.
6. [Interface com computador por Controlo Visual de Cursores-Calibração do Sistema](https://web.fe.up.pt/~ee97107/Relatorio_de_Projecto_FINAL_PARTE_2.pdf)
7. [Borislav Kostov-photography](https://borislavkostov.wordpress.com/articles/macro-photography-eng/focal-length-focusing-distance-working-distance/)
8. [Câmera Sensor Size Guide](https://newatlas.com/camera-sensor-size-guide/26684/)
9. [Photography Life F-stop](https://photographylife.com/f-stop)
10. Multiple View Geometry in Computer Vision Second Edition, Richard Hartley and Andrew Zisserman, Cambridge University Press, March 2004.
11. [Blender](https://www.blender.org/)
12. [Sketchfab](https://sketchfab.com/feed)
13. [Blender-Addons](https://github.com/lightfield-analysis/blender-addon)
14. [4D LightField Benchmark](https://lightfield-analysis.uni-konstanz.de/tools.html)
15. Katrin Honauer, Ole Johannsen, Daniel Kondermann, Bastian Goldluecke, ["A Dataset and Evaluation Methodology for
Depth Estimation on 4D Light Fields"](http://lightfield-analysis.net/benchmark/paper/lightfield_benchmark_accv_2016.pdf)
16. Ting-Chun Wang, Jun-Yan Zhu, Nima Khademi Kalantari, Alexei A. Efros, Ravi Ramamoorthi, ["Light Field Video Capture Using a Learning-Based Hybrid Imaging System"](http://cseweb.ucsd.edu/~viscomp/projects/LF/papers/SIG17/lfv/), ACM Transactions on Graphics (Proceedings of SIGGRAPH 2017), 36, 4, 2017.
17. [LightField Video](https://github.com/junyanz/light-field-video).
18. [MatLab](https://www.mathworks.com/products/matlab.html)
