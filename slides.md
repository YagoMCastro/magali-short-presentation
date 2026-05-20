<!--
-------------------------------------------------------------------------------
This file defines the contents of each slide.
The reveal.js configuration can be found in index.html
-------------------------------------------------------------------------------
-->

<!-- .slide: class="slide-title" data-background-opacity="0.3" data-background-image="assets/magali-logo.svg" data-background-color="#000000" data-background-size="contain" -->

<!-- Place the content at the bottom of the slide -->
<div class="r-stretch">
</div>

<h1 id="talk-title">
  
Magali: uma ferramenta aberta para a comunidade de microscopia
magnética

</h1>
<p id="talk-authors">
  <a id="talk-speaker"><b>Yago Moreira Castro</b></a>,
  Leonardo Uieda
</p>

<!-- Place location and date side-by-side with affiliation logos -->
<div class="row talk-info">
<div class="col-large">

<i class="fa fa-calendar-alt" style="margin: 0 10px 0 0"></i>
05 de Março  de 2025
<span style="margin: 0 20px"></span>
Defesa de Mestrado em Geofísica | São Paulo, Brasil

<!-- Permission to reuse and CC-BY license logo -->
<i class="fa fa-camera" style="margin: 0 10px 0 0"></i>
Sinta-se à vontade para fotografar/compartilhar/reutilizar esta apresentação

<span style="margin: 0 20px"></span>
<a href="https://creativecommons.org/licenses/by/4.0/"><i class="fab fa-creative-commons"></i><i class="fab fa-creative-commons-by" style="margin: 0 10px 0 2px"></i>CC-BY 4.0 License</a>

</div>
<div class="col-medium">

<!-- Add logos here. Need these wrappers to align them to the bottom right -->
<div class="talk-logos-container">
<div class="talk-logos">
  <a href="https://www.compgeolab.org"><img src="assets/compgeolab-banner-light.svg" alt="Computer-Oriented Geoscience Lab"></a>
  <a href="https://www.iag.usp.br/"><img src="assets/iag.png" alt="Instituto de Astronomia, Geofísica e Ciências Atmosféricas"></a>
  <a href="https://www.gov.br/capes/pt-br"><img src="assets/capes.png" alt="CAPES"></a>
</div>
</div>
</div>
</div>

===============================================================================
# Sumário
<ul style="list-style: none">
  <li  style="color: red !important;"><b>Paleomagnetismo</b></li>
  <li><b>Microscopia magnética</b></li>
  <li>
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Fundamentação Teórica</li>
      <li>Desenvolvimento de software</li>
    </ul>
  </li>
  <li><b>Comparação de Performance e Acurácia</b></li>  
  <li><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li><b>Conclusões</b></li>
</ul>

===============================================================================
# O que é Paleomagnetismo?
<div class="quote">

Aplicação de medições magnéticas de minerais de rochas para resolver problemas geológicos


</div>
<div class="footnote-center">

[Notas de aula de Lisa Tauxe](https://magician.ucsd.edu/SIO247/)
</div>

===============================================================================
# Como os minerais são magnetizados?

- <!-- .element: class="fragment" -->
  - **Magnetização Remanente Termal (TRM):** rochas ígneas registram o campo magnético  à medida que esfriam abaixo do ponto de Curie (ex.: magnetita pura: **580°C**)

- <!-- .element: class="fragment" -->
  - **Magnetização Remanente Deposicional (DRM):** partículas magnéticas em sedimentos se alinham com o campo magnético da Terra durante a deposição em ambientes aquáticos

===============================================================================
# Por que o paleomagnetismo é importante?

- <!-- .element: class="fragment" -->
  - **Reversões geomagnéticas** mostram que o campo magnético da Terra já se **inverteu** muitas vezes ao longo de sua história

- <!-- .element: class="fragment" -->
  - Ajudou a confirmar a teoria da **deriva continental** e a reconstruir as **posições** passadas dos continentes

- <!-- .element: class="fragment" -->
  - Utilizado como ferramenta de **datação relativa** ao comparar registros em rochas com a escala de tempo conhecida das reversões magnéticas **(magnetoestratigrafia)**

- <!-- .element: class="fragment" -->
  - Permite compreender como o **campo magnético** terrestre **evoluiu** ao longo de centenas de milhões de anos

===============================================================================
# Tipos de Grãos Magnéticos
<div class="text-left fragment">

- **Multidomínio (MD):** são grãos maiores que se subdividem em vários domínios, cada um apontando em direções diferentes. Isto reduz a estabilidade magnética, tornando-os registradores pouco confiáveis
</div>

<div class="text-left fragment">

- **Domínio Único (SD):** são grãos pequenos em que a magnetização permanece uniforme e alinhada em uma única direção, apresentando altíssima estabilidade
</div>

<div class="text-left fragment">

- **Pseudo-Domínio Único (PSD):** apresentam tamanhos intermediários, podem registrar o campo magnético com elevada fidelidade e estabilidade, contrariando interpretações mais antigas que os consideravam menos confiáveis
</div>

===============================================================================
# Limitações do Paleomagnetismo
<div class="text-left fragment">

- Sobreposição com **magnetizações secundárias** e impossibilidade de **separar o sinal** de minerais diferentes **sem alterar** propriedades da amostra (ex: magnetita vs. hematita)
</div>

<div class="text-left fragment">

- Amostras com **sinais muito fracos** não superam o ruído de fundo dos magnetômetros convencionais
</div>

<div class="text-left fragment">

- Diversos métodos **alteram a amostra**, seja alterando a magnetização ou destruindo-a
</div>

===============================================================================
<div class="r-stretch">
  <img src="assets/sample.svg" height=100%>
</div>

===============================================================================
<div class="r-stretch">
  <img src="assets/arrow.svg" height=100%>
</div>

===============================================================================
# Sumário

<ul style="list-style: none">
  <li><b>Paleomagnetismo</b></li>
  <li style="color: red !important;"><b>Microscopia magnética</b></li>
  <li>
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Fundamentação Teórica</li>
      <li>Desenvolvimento de software</li>
    </ul>
  </li>
  <li><b>Comparação de Performance e Acurácia</b></li>  
  <li><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li><b>Conclusões</b></li>
</ul>

===============================================================================
# Quantum Diamond Microscope

<div class="text-left fragment">

- Utiliza uma placa de diamante sintético com defeitos cristalinos chamados **Centros Nitrogênio-Vacância (NV)**
</div>

<div class="text-left fragment">

- Ao receber um laser verde e micro-ondas, os centros NV emitem uma luz. A **intensidade dessa fluorescência** é alterada de acordo com o **campo magnético** da rocha próxima ao diamante
</div>

<div class="text-left fragment">

- Uma câmera captura essa luz e gera um **mapa do campo magnético** da superfície medida com resolução espacial **micrométrica**
</div>

<div class="text-left fragment">

- Diferente de sensores criogênicos, o QDM opera em **temperatura ambiente**, simplificando a **logística laboratorial**
</div>

===============================================================================
<div class="r-stretch">

  <img src="assets/qdm.jpg" height=115%>

</div>
<br>
<div class="footnote-left">

[Harvard Paleomagnetics Lab](https://paleomag.fas.harvard.edu/laboratory)
</div>

===============================================================================

<!-- .slide: class="slide-title" data-background-opacity="1" data-background-image="assets/ceramic.png"  data-background-size="contain" -->

<div class="r-stretch">
</div>
<div class="footnote-center">

[Souza-Junior et al 2025](https://eartharxiv.org/repository/view/8869/)
</div>

===============================================================================
# Temos um problema

===============================================================================
<img src="assets/berndt_paper.png" style="width: 80%">

- $10^7$ a $10^9$ de grãos seriam necessários para uma rocha obter direções confiáveis

===============================================================================
<img src="assets/bellon_paper.png" style="width: 80%">

===============================================================================
# Bellon et al. (2025)

<div class="text-left">

- **Investigaram** a aquisição de TRM por milhares de partículas nanoscópicas no **estado de vórtex**

</div>
<div class="fragment text-left">

- **Simularam** o comportamento desses conjuntos sob diversas intensidades de campos magnéticos

</div>
<div class="fragment text-left">

- **Demonstraram** que o quando as partículas são afetadas com campos maiores que **20 μT**, o paleocampo é registrado com extrema precisão (**erro angular < 1°**)

</div>

<div class="footnote-center">

[Bellon et al. (2025)](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2025GL114771)
</div>

===============================================================================

<!-- .slide: class="slide-title" data-background-opacity="1" data-background-image="assets/ceramic.png"  data-background-size="contain" -->

<div class="r-stretch">
</div>
<div class="footnote-center">

[Souza-Junior et al 2025](https://eartharxiv.org/repository/view/8869/)
</div>


===============================================================================
<img src="assets/paper_2.png" style="width: 80%" >

===============================================================================
<p class="text-left fragment" data-fragment-index="0">
  <b>Etapa 1 - Detecção da fonte</b>
</p>

<p class="text-left fragment" data-fragment-index="1">
  <b>Etapa 2 - Processamento iterativo (por janela)</b>
</p>

<ul>
  <li class="text-left fragment" data-fragment-index="2">
    (a) <b>Isolamento dos dados:</b> selecionar os dados magnéticos dentro da janela
  </li>
  <li class="text-left fragment" data-fragment-index="3">
    (b) <b>Deconvolução de Euler:</b> estimar a <em>posição</em> da fonte
  </li>
  <li class="text-left fragment" data-fragment-index="4">
    (c) <b>Inversão linear:</b> estimar o <em>momento</em> do dipolo usando posição fixa
  </li>
  <li class="text-left fragment" data-fragment-index="5">
    (d) <b>Inversão não linear:</b> refinar posição e momento via 
    <a href="https://academic.oup.com/comjnl/article-abstract/7/4/308/354237?redirectedFrom=fulltext">Nelder-Mead</a>
  </li>
  <li class="text-left fragment" data-fragment-index="7">
    (e) <b>Remoção do sinal:</b> modelar o dipolo diretamente e subtrair do conjunto de dados completo
  </li>
</ul>
<p class="text-left fragment" data-fragment-index="8">
  <b>Etapa 3 - Repetir a detecção nos dados residuais:</b>
  aplicar as etapas 1 e 2 ao conjunto de dados residual
</p>

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/readme-banner.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="0.2" data-background-image="assets/magali-logo.png"  data-background-size="contain" data-background-color="#262626" -->

# Por que queremos desenvolvê-lo?
<div class="fragment text-left">

- Fornecer um código **fácil de usar**
</div>
<div class="fragment text-left">

- Determinar as **posições espaciais** de **múltiplos** grãos
</div>
<div class="fragment text-left">

- Facilitar a criação de **dados sintéticos**
</div>
<div class="fragment text-left">

- Propor um **formato padrão de dados**
</div>
<div class="fragment text-left">

- Servir como **base** para desenvolvimento de novos métodos
</div>
<div class="fragment text-left">

- Explorar o potencial de estudos emergentes em **microscopia magnética**
</div>

===============================================================================
<!-- .slide: data-background-opacity="0.2" data-background-image="assets/magali-logo.png"  data-background-size="contain" data-background-color="#262626" -->
<div class="huge">

Magali

<div class="large fragment">

Biblioteca em Python <br><i class="fab fa-python"></i>

</div>

<div class="large fragment">

Software livre e de código aberto  

<i class="fab fa-github"></i> <i class="fas fa-lock-open"></i> <i class="fab fa-osi"></i>

</div>

</div>
<div class="large fragment">

Modelagem e processamento de dados de microscopia magnética  
<i class="fas fa-magnet"></i> <i class="fas fa-microscope"></i>

</div>

===============================================================================
# Sumário
<ul style="list-style: none">
  <li><b>Paleomagnetismo</b></li>
  <li><b>Microscopia magnética</b></li>
  <li style="color: red !important;">
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Fundamentação Teórica</li>
      <li>Desenvolvimento de software</li>
    </ul>
  </li>
  <li><b>Comparação de Performance e Acurácia</b></li>  
  <li><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li><b>Conclusões</b></li>
</ul>

===============================================================================
<h2>Etapa 1: Detecção da Fonte</h2>
  
<p class="text-left">
  <b>Objetivo:</b> isolar cada partícula magnética na imagem
</p>

<p class="text-left fragment">
  <b>Métodos utilizados:</b>
</p>

<ul>
  <li class="fragment">
    <b>Continuação para cima:</b> atenua ruídos de alta frequência (filtro passa-baixa) e estabiliza o campo para o cálculo de gradientes 
  </li>
</ul>

===============================================================================
<div class="row">
<div class="col"><img src="assets/qdm_data.png" style="width: 100%" ></div>
<div class="col"><img src="assets/data_up.png" style="width: 100%" ></div>
</div>

Continuação para cima de $5 \mu m$

===============================================================================
<h2>Etapa 1: Detecção da Fonte</h2>
  
<p class="text-left">
  <b>Objetivo:</b> isolar cada partícula magnética na imagem
</p>

<p class="text-left">
  <b>Métodos utilizados:</b>
</p>

<ul>
  <li >
    <b>Continuação para cima:</b> atenua ruídos de alta frequência (filtro passa-baixa) e estabiliza o campo para o cálculo de gradientes 
  </li>
  <li>
    <b>Amplitude do Gradiente Total (TGA):</b> realça o sinal próximo à fonte através de um filtro passa-alta
  </li>
</ul>

===============================================================================
# Derivadas e TGA
<div class="text-left">

- Calcula-se a **Amplitude do Gradiente Total (TGA)** de uma função harmônica (podendo ser o campo magnético) definida como a norma do vetor gradiente:

$$||\vec{\mathbf{\nabla}}f(x, y, z)|| = \sqrt{(\partial_x f)^2 + (\partial_y f)^2 + (\partial_z f)^2}$$

</div>

<div class="footnote-center">

[Blakely (1995)](https://www.cambridge.org/core/books/potential-theory-in-gravity-and-magnetic-applications/348880F23008E16E663D6AD14A41D8DE)
</div>

===============================================================================
# Derivadas e TGA
<div class="text-left">

- No dado continuado para cima, **aproximam-se** as derivadas horizontais utilizando um esquema de **diferenças finitas centrais** de segunda ordem (assumindo espaçamento uniforme $\Delta x$ e $\Delta y$):

$$\partial_x f(x, y, z) \approx \frac{f(x + \Delta x, y, z) - f(x - \Delta x, y, z)}{2 \Delta x}$$

$$\partial_y f(x, y, z) \approx \frac{f(x, y + \Delta y, z) - f(x , y + \Delta y, z)}{2 \Delta y}$$

</div>


===============================================================================
# Cálculo em Z
<div class="text-left">

- **Obtem-se** as variações no eixo vertical ($f(z + \Delta z)$ e $f(z - \Delta z)$) aplicando **continuação para cima** no dado original a uma altura abaixo e uma acima do anteriormente continuado

</div>

<div class="footnote-center">

[Souza-Junior et al. (2025)](https://eartharxiv.org/repository/view/8869/)

</div>

===============================================================================
# Vantagens do TGA

<div class="text-left fragment">

- Gera valores **estritamente positivos**
</div>


<div class="text-left fragment">

- **Centraliza** os picos diretamente sobre as **fontes magnéticas**
</div>


<div class="text-left fragment">

- **Minimiza** a dependência da **direção de magnetização** original
</div>


<div class="text-left fragment">

- Atua como um filtro **passa-alta**, removendo ruídos de **longo comprimento de onda**
</div>

===============================================================================
<div class="row">
<div class="col"><img src="assets/data_up.png" style="width: 100%" ></div>
<div class="col"><img src="assets/tga.png" style="width: 80%" ></div>
</div>

===============================================================================
<h2>Etapa 1: Detecção da Fonte</h2>
  
<p class="text-left">
  <b>Objetivo:</b> isolar cada partícula magnética na imagem
</p>

<p class="text-left">
  <b>Métodos utilizados:</b>
</p>

<ul>
  <li >
    <b>Continuação para cima:</b> atenua ruídos de alta frequência (filtro passa-baixa) e estabiliza o campo para o cálculo de gradientes 
  </li>
  <li>
    <b>Amplitude do Gradiente Total (TGA):</b> realça o sinal próximo à fonte através de um filtro passa-alta
  </li>
  <li>
    <b>Realce de contraste:</b> utiliza percentis (1º a 99º) para destacar partículas de baixa intensidade
  </li>
</ul>

===============================================================================
# Realce de Contraste

- **Objetivo**: reescalonar os valores de TGA para destacar sinais fracos e fortes 
- **Operação**: transformação por pixel para normalizar os dados:

<p>
\[
\text{TGA}_{\text{rescaled}} = 2 \left( \frac{\text{TGA} - v_{\min}}{v_{\max} - v_{\min}} \right) - 1
\]
</p>

<ul>
<li>$ v_{\text{min}} = 1^\text{º} $ percentil</li>
<li>$ v_{\text{max}} = 99^\text{º} $ percentil</li>
<li><b>Saída:</b> valores reescalados para o intervalo $[0, 1]$</li>
</ul>

===============================================================================
<div class="row">
  <div class="col">
    <img src="assets/tga.png" style="width: 80%">
  </div>
  <div class="col">
    <img src="assets/stretched.png" style="width: 100%">
  </div>
</div>


===============================================================================
<div class="row">
<div class="col"><img src="assets/data_up.png" style="width: 100%" ></div>
<div class="col"><img src="assets/stretched.png" style="width: 100%" ></div>
</div>

===============================================================================
<h2>Etapa 1: Detecção da Fonte</h2>
<p class="text-left">
  <b>Objetivo:</b> isolar cada partícula magnética na imagem
</p>

<p class="text-left">
  <b>Métodos utilizados:</b>
</p>

<ul>
  <li >
    <b>Continuação para cima:</b> atenua ruídos de alta frequência (filtro passa-baixa) e estabiliza o campo para o cálculo de gradientes 
  </li>
  <li>
    <b>Amplitude do Gradiente Total (TGA):</b> realça o sinal próximo à fonte através de um filtro passa-alta
  </li>
  <li>
    <b>Realce de contraste:</b> utiliza percentis (1º a 99º) para destacar partículas de baixa intensidade
  </li>
  <li>
    <b>Segmentação LoG (Laplaciano do Gaussiano):</b> detecta “blobs” e define uma janela individual por partícula e as organiza por intensidade de sinal decrescente para o processamento iterativo
  </li>
</ul>


===============================================================================
# Filtro LoG
<div class="text-left">

- **Suavizamos** a imagem primeiro com um kernel Gaussiano para **eliminar ruídos de alta frequência**:

$$G(x, y; \sigma) = \frac{1}{2\pi\sigma^2} e^{-\frac{x^2 + y^2}{2\sigma^2}}$$

- $\sigma$: parâmetro de escala

<div class="footnote-center">

**Kernel** funciona como um filtro que é convolvido com a imagem
</div>
</div>

===============================================================================
# Filtro LoG

<div class="text-left">

- Aplicamos o operador **Laplaciano** (soma das derivadas de segunda ordem) para destacar zonas de **variação rápida**:

$$\nabla \cdot \nabla G(x, y; \sigma) = \frac{x^2 + y^2 - 2\sigma^2}{2\pi\sigma^4} e^{-\frac{x^2 + y^2}{2\sigma^2}}$$

</div>

===============================================================================
<div class="row">
  <div class="col">
    <img src="assets/stretched.png" style="width: 100%">
  </div>
  <div class="col">
    <img src="assets/detection.png" style="width: 100%">
  </div>
</div>

===============================================================================
# Deconvolução de Euler

<div class="text-left">

- É um método baseado na equação de homogeneidade de Euler para estimar a <b>localização</b> e a <b>profundidade</b> de fontes magnéticas
</div>

<div class="text-left fragment">

- Para este método assume-se um modelo de **fonte dipolar**</li>

</div>

===============================================================================
# Equação de Homogeneidade de Euler

$$
(\mathbf{x}-\mathbf{v})\cdot \nabla f = (b-f)\eta
$$

<div class="text-left">
<ul>
  <li class="fragment">$\mathbf{x}=[x,y,z]^T$ : coordenadas dos dados</li>
  <li class="fragment">$\mathbf{v}=[x_c,y_c,z_c]^T$ : coordenadas da fonte do campo magnético</li>
  <li class="fragment">$f$ : função homogênea (ex.: $b_z$)</li>
  <li class="fragment">$b$ : nível de base (deslocamento constante do sinal)</li>
  <li class="fragment">$\eta$ : índice estrutural ($\eta=3$ para dipolos)</li>
</ul>
</div>

<div class="footnote-center">

[Reid et al. 1990](https://pubs.geoscienceworld.org/seg/geophysics/article-abstract/55/1/80/72314/Magnetic-interpretation-in-three-dimensions-using?redirectedFrom=fulltext)

</div>


===============================================================================
# Equação de Homogeneidade de Euler

$$
(\mathbf{x}-\mathbf{v})\cdot \nabla f = (b-f)\eta
$$

<div class="quote">

A taxa de **variação do campo** ($\nabla f$) multiplicada pela **distância vetorial** ($\mathbf{x}-\mathbf{v}$) é proporcional à **amplitude do campo medido** ($b-f$)
</div>

<div class="footnote-center">

[Reid et al. 1990](https://pubs.geoscienceworld.org/seg/geophysics/article-abstract/55/1/80/72314/Magnetic-interpretation-in-three-dimensions-using?redirectedFrom=fulltext)

</div>

===============================================================================
# Equação de Homogeneidade de Euler

$$
(x - x_c)\partial_x f + (y - y_c)\partial_y f + (z - z_c)\partial_z f = (b - f)\eta
$$ 
<p class="fragment"> Isolar os parâmetros parâmetros $x_c, y_c, z_c, b$</p>
<div class="fragment">

$$
\underbrace{x_c \partial_x f + y_c \partial_y f + z_c \partial_z f + \eta b}_\text{Com parâmetros} = \underbrace{x \partial_x f + y \partial_y f + z \partial_z f + \eta f}_\text{Sem parâmetros}
$$
</div>
<div class="footnote-center">

[Reid et al. 1990](https://pubs.geoscienceworld.org/seg/geophysics/article-abstract/55/1/80/72314/Magnetic-interpretation-in-three-dimensions-using?redirectedFrom=fulltext)
[Souza-Junior et al. 2024](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023GC011082)
</div>

===============================================================================
# Equação de Homogeneidade de Euler

$$
x_c \ \partial_x f + y_c \ \partial_y f + z_c \ \partial_z f + \eta b
=
x \ \partial_x f + y \ \partial_y f + z \ \partial_z f + \eta f
$$

<p class="fragment">Aplicamos a cada ponto de dado, forma-se um sistema linear $N \times 4$</p>

<p class="fragment">
\[
\underbrace{
\begin{bmatrix}
\partial_x f_1 & \partial_y f_1 & \partial_z f_1 & \eta \\
\partial_x f_2 & \partial_y f_2 & \partial_z f_2 & \eta \\
\vdots & \vdots & \vdots & \vdots \\
\partial_x f_N & \partial_y f_N & \partial_z f_N & \eta
\end{bmatrix}
}_{\text{Matriz Jacobiana}}
\underbrace{
\begin{bmatrix}
x_c \\ y_c \\ z_c \\ b
\end{bmatrix}
}_{\text{Vetor de parâmetros}}
=
\underbrace{
\begin{bmatrix}
x_1 \partial_x f_1 + y_1 \partial_y f_1 + z_1 \partial_z f_1 + \eta f_1 \\
x_2 \partial_x f_2 + y_2 \partial_y f_2 + z_2 \partial_z f_2 + \eta f_2 \\
\vdots \\
x_N \partial_x f_N + y_N \partial_y f_N + z_N \partial_z f_N + \eta f_N
\end{bmatrix}
}_{\text{Vetor de pseudodados}}
\]
</p>

<div class="fragment">

$$\mathbf{Gp=h}$$

</div>
<div class="footnote-center">

[Reid et al. 1990](https://pubs.geoscienceworld.org/seg/geophysics/article-abstract/55/1/80/72314/Magnetic-interpretation-in-three-dimensions-using?redirectedFrom=fulltext)
[Souza-Junior et al. 2024](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2023GC011082)
</div>

===============================================================================
# Solução por mínimos quadrados

$$
\mathbf{G} \mathbf{p} = \mathbf{h}
$$

<div class="text-left fragment">

<p class="text-left">Cuja função objetivo é:</p>

$$
\Phi (\mathbf{p}) = ||\mathbf{h}^o - \mathbf{h}||^2
$$

<ul>
  <li>$\Phi (\mathbf{p})$ : função objetivo</li>
  <li>$\mathbf{h}^o$ : dados observados</li>
  <li>$\mathbf{h}$ : dados preditos</li>
</ul>

</div>

===============================================================================
<ol>
  <li>
    <b>Expandindo a expressão:</b><br>
    \[
    \Phi(\mathbf{p}) = (\mathbf{h}^o - \mathbf{G}\mathbf{p})^\top (\mathbf{h}^o - \mathbf{G}\mathbf{p}) = \underbrace{\mathbf{h}^{o\top}\mathbf{h}^o - 2\mathbf{p}^\top \mathbf{G}^\top \mathbf{h}^o + \mathbf{p}^\top \mathbf{G}^\top \mathbf{G} \mathbf{p}}_\text{Paraboloide}
    \]
  </li>
  <li class="fragment">
    <b>Utilizamos o gradiente em respeito a \(\mathbf{p}\) e atribuímos zero:</b><br>
    \[
      \nabla_{\mathbf{p}} \Phi(\mathbf{p}) = -2 \mathbf{G}^\top \mathbf{h}^o + 2 \mathbf{G}^\top \mathbf{G} \mathbf{p}=\mathbf{0}
    \]
    \[
      \boxed{
      \mathbf{G}^\top \mathbf{G} \mathbf{p} = \mathbf{G}^\top \mathbf{h}^o
      }
    \]
    \[
      \boxed{
        \mathbf{p} = (\mathbf{G}^\top \mathbf{G})^{-1} \mathbf{G}^\top \mathbf{h}^o
      }
    \]
  </li>
  <li class="text-center fragment">
    <b>Assim estimamos $x_c$, $y_c$, $z_c$ e $b$</b><br>
  </li>
</ol>

===============================================================================
# Inversão linear
## Modelo de Campo de Dipolo
<p class="text-left">O campo $\mathbf{b}$ gerado por um dipolo $\mathbf{m} = [m_x \ m_y \ m_z]^\top$:</p>
$$
\mathbf{b} = 
\begin{bmatrix}
b_x \\
b_y \\
b_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi}
\begin{bmatrix}
\frac{\partial^2}{\partial x \partial x} \frac{1}{r} & \frac{\partial^2}{\partial x \partial y} \frac{1}{r} & \frac{\partial^2}{\partial x \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial y \partial x} \frac{1}{r} & \frac{\partial^2}{\partial y \partial y} \frac{1}{r} & \frac{\partial^2}{\partial y \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} & \frac{\partial^2}{\partial z \partial y} \frac{1}{r} & \frac{\partial^2}{\partial z \partial z} \frac{1}{r}
\end{bmatrix}
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi} \mathbf{M} \mathbf{m}
$$
<br>
<div class="text-left"><ul>
<li> $r=\sqrt{(x-x_c)^2+(y-y_c)^2+(z-z_c)^2}$: distância cartesiana entre os pontos de observação e da fonte</li>
<li> $\mu_0$ : permeabilidade magnética no vácuo</li>
</ul></div>

===============================================================================
<h1>Sistema para $b_z$</h1>
<p>
\[
\mathbf{b} = 
\begin{bmatrix}
b_x \\
b_y \\
b_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi}
\begin{bmatrix}
\frac{\partial^2}{\partial x \partial x} \frac{1}{r} & \frac{\partial^2}{\partial x \partial y} \frac{1}{r} & \frac{\partial^2}{\partial x \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial y \partial x} \frac{1}{r} & \frac{\partial^2}{\partial y \partial y} \frac{1}{r} & \frac{\partial^2}{\partial y \partial z} \frac{1}{r} \\
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} & \frac{\partial^2}{\partial z \partial y} \frac{1}{r} & \frac{\partial^2}{\partial z \partial z} \frac{1}{r}
\end{bmatrix}
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}
=
\frac{\mu_0}{4\pi} \mathbf{M} \mathbf{m}
\]</p>

$$
b_z = 
\frac{\mu_0}{4\pi}
\begin{bmatrix}
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} & \frac{\partial^2}{\partial z \partial y} \frac{1}{r} & \frac{\partial^2}{\partial z \partial z} \frac{1}{r}
\end{bmatrix}
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}^\top 
$$

===============================================================================
$$
\frac{\partial^2}{\partial z \partial x} \frac{1}{r} = \frac{3(z - z_c)(x - x_c)}{r^5}
$$
$$
\frac{\partial^2}{\partial z \partial y} \frac{1}{r} = \frac{3(z - z_c)(y - y_c)}{r^5}
$$
$$
\frac{\partial^2}{\partial z \partial z} \frac{1}{r} = \frac{3(z - z_c)^2}{r^5} - \frac{1}{r^3}
$$

===============================================================================
# Formulação do Problema
<p class="text-left">
Dadas $N$ observações de $b_z$ em uma janela contendo uma única fonte,
forma-se um sistema linear $N \times 3$:
</p>
\[
\underbrace{  
\begin{bmatrix}
\frac{\mu_0}{4\pi} \frac{3(z_1 - z_c)(x_1 - x_c)}{r_1^5} & \frac{\mu_0}{4\pi} \frac{3(z_1 - z_c)(y_1 - y_c)}{r_1^5} & \frac{\mu_0}{4\pi} \left( \frac{3(z_1 - z_c)^2}{r_1^5} - \frac{1}{r_1^3} \right) \\
\frac{\mu_0}{4\pi} \frac{3(z_2 - z_c)(x_2 - x_c)}{r_2^5} & \frac{\mu_0}{4\pi} \frac{3(z_2 - z_c)(y_2 - y_c)}{r_2^5} & \frac{\mu_0}{4\pi} \left( \frac{3(z_2 - z_c)^2}{r_2^5} - \frac{1}{r_2^3} \right) \\
\vdots & \vdots & \vdots \\
\frac{\mu_0}{4\pi} \frac{3(z_N - z_c)(x_N - x_c)}{r_N^5} & \frac{\mu_0}{4\pi} \frac{3(z_N - z_c)(y_N - y_c)}{r_N^5} & \frac{\mu_0}{4\pi} \left( \frac{3(z_N - z_c)^2}{r_N^5} - \frac{1}{r_N^3} \right)
\end{bmatrix}}_{\text{Jacobiana}}
\underbrace{
\begin{bmatrix}
m_x \\
m_y \\
m_z
\end{bmatrix}}_{\text{Parâmetros}}
=
\underbrace{
\begin{bmatrix}
b_{z_1} \\
b_{z_2} \\
\vdots \\
b_{z_N}
\end{bmatrix}}_{\text{Observação}}
\]
<p class="fragment">$$\mathbf{Am=d^o}$$</p>

===============================================================================
# Estimativa por Mínimos Quadrados
<p class="text-left">Minimiza-se a função objetivo:</p>

$$\Gamma(\mathbf{m}) = \|\mathbf{d}^{o}-\mathbf{A}\mathbf{m}\|^2=(\mathbf{d}^{o}-\mathbf{A}\mathbf{m})^T(\mathbf{d}^{o}-\mathbf{A}\mathbf{m})$$
<p class="text-left">O que leva às equações normais:</p>
$$\mathbf{A}^T\mathbf{A}\mathbf{m} = \mathbf{A}^T\mathbf{d}^{o}$$

<p class="fragment">A solução fornece o <b>momento de dipolo estimado ($\mathbf{m}$)</b></p>


===============================================================================
<div class="text-left" >

- Temos estimativas de **momentos** e **posição**
</div>

<div class="text-left fragment">

- A Deconvolução de Euler não estima tão bem a **profundidade**
</div>

<div class="text-left fragment">

- Problema das **fontes interferentes** 
</div>

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/simple-model-2.png"  data-background-size="contain" data-background-color="#262626" -->


===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/one-interf-2.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<p class="text-left">
  <b>Etapa 1 - Detecção da fonte</b>
</p>

<p class="text-left">
  <b>Etapa 2 - Processamento iterativo (por janela)</b>
</p>

<ul>
  <li class="text-left">
    (a) <b>Isolamento dos dados:</b>
    selecionar os dados magnéticos dentro da janela
  </li>

  <li class="text-left">
    (b) <b>Deconvolução de Euler:</b>
    estimar a posição da fonte
  </li>

  <li class="text-left">
    (c) <b>Inversão linear:</b>
    estimar o momento do dipolo usando posição fixa
  </li>

  <li style="color: red !important;" class="text-left">
    (d) <b>Inversão híbrida:</b>
    refinar posição e momento via
    <b>Levenberg–Marquardt</b>
  </li>

  <li class="text-left">
    (e) <b>Remoção do sinal:</b>
    modelar o dipolo diretamente e subtrair do conjunto de dados completo
  </li>
</ul>

<p class="text-left">
  <b>Etapa 3 - Repetir a detecção nos dados residuais:</b>
  aplicar as etapas 1 e 2 ao conjunto de dados residual
</p>

===============================================================================
# Aspectos importantes
<div class="fragment text-left">

- Para uma localização fixa ($\mathbf{v}$), o campo magnético **depende linearmente** do momento magnético ($\mathbf{m}$)

</div>
<div class="fragment text-left">

- Evitamos o **acoplamento direto** de parâmetros com **ordens de magnitude muito diferentes**. Em inversões simultâneas, a diferença entre a escala da localização (**10⁻⁶ m**) e do momento (**10⁻¹³ Am²**) dificulta a convergência

</div>
<div class="fragment text-left">

- Garantimos um problema **bem escalonado** ao separar a inversão em **grupos fisicamente homogêneos**, dispensando a necessidade de **normalizações** explícitas de parâmetros

</div>

===============================================================================
# Inversão Híbrida
<ul>
  <li class="fragment">
    <b>1. Inicialização:</b> chute inicial de posição ($\mathbf{v}$) obtido via Deconvolução de Euler
  </li>
  
  <li class="fragment">
    <b>2. Inversão acoplada (Loop Principal):</b>
    <ul>
      <li class="fragment">
        (A) <b>Estimativa linear:</b> fixa a posição e calcula o momento ($\mathbf{m}$)
      </li>
      <li class="fragment">
        (B) <b>Atualização não linear:</b> refina a posição da fonte ($\mathbf{v}$) via algoritmo Levenberg-Marquardt
      </li>
    </ul>
  </li>
  <li class="fragment">
    <b>3. Convergência:</b> o processo encerra quando a redução do valor da função objetivo atinge a tolerância  de $10^{-2}$ 
  </li>
</ul>

===============================================================================
# Otimização via Levenberg-Marquardt
<div class="fragment text-left">

- Utilizamos este método por ser **baseado em gradiente**, sendo melhor optimizado quando comparado a métodos que **independem de derivadas**, como Nelder-Mead, para problemas **suaves e diferenciáveis**

</div>
<div class="fragment text-left">

- Minimizamos a função objetivo a partir do método de mínimos quadrados $\Psi(\mathbf{v})$:

$$\Psi(\mathbf{v}) = \| \mathbf{d}^o - \mathbf{d}(\mathbf{v}) \|^2$$

- $\mathbf{v}$: posição
- $\mathbf{d}^o$: dados observados do campo magnético
- $\mathbf{d}(\mathbf{v})$: dados preditos

</div>

===============================================================================
# Inversão Híbrida
<div class="fragment text-left">

- Atualizamos a localização resolvendo o sistema amortecido para o incremento ($\Delta \mathbf{v})$:

$$\left( \mathbf{J}^T \mathbf{J} + \alpha \cdot \mathrm{diag}(\mathbf{J}^T \mathbf{J}) \right) \Delta\mathbf{v} = \mathbf{J}^T \big( \mathbf{d}^o - \mathbf{d}(\mathbf{v}) \big)$$

- $\mathbf{J}$: matriz Jacobiana
- $\mathbf{J}^T \mathbf{J}$: aproximação da Hessiana
- $(\mathbf{d}^o - \mathbf{d}(\mathbf{v}))$: vetor de resíduos
- $\alpha \cdot \mathrm{diag}(\mathbf{J}^T \mathbf{J})$: amortecimento escalonado pela curvatura local
</div>

===============================================================================
# Parâmetro de Marquardt 
<div class="text-left">

- Inicializamos o **parâmetro de Marquardt ($\alpha$)** de forma não arbitrária, baseando-nos na mediana da diagonal da aproximação Hessiana para o condicionamento do sistema:

$$\alpha = S \cdot \text{median}(\text{diag}(\mathbf{J}^T\mathbf{J})) \quad \text{, } S = 10^{-20}$$

</div>

===============================================================================
$$\left( \mathbf{J}^T \mathbf{J} + \alpha \cdot \mathrm{diag}(\mathbf{J}^T \mathbf{J}) \right) \Delta\mathbf{v} = \mathbf{J}^T \big( \mathbf{d}^o - \mathbf{d}(\mathbf{v}) \big)$$

<div class="fragment text-left">

- Ajustamos $\alpha$ dinamicamente via estratégia de **região de confiança**:
  - **$\downarrow$ valor da função objetivo = Sucesso:** aceitamos $\Delta \mathbf{v}$ e dividimos $\alpha$ por 10 tendendo a **Gauss-Newton**
    - Utiliza a curvatura da Hessiana ($\mathbf{J}^T \mathbf{J}$) para dar passos longos
  - **$\uparrow$ valor da função objetivo = Falha:** rejeitamos $\Delta \mathbf{v}$ e multiplicamos $\alpha$ por 10 tendendo a **Steepest Descent**
    - O termo diagonal domina, fazendo o passo seguir a direção do gradiente negativo

</div>

===============================================================================
# Estabilidade 
<div class="text-left">

- Limitamos o deslocamento máximo por iteração ($\|\Delta \mathbf{v}\| \le 10\mu m$) para evitar atualizações que não façam sentido fisicamente e garantir que a solução permaneça dentro da janela de dados

</div>

===============================================================================
# Recapitulando

===============================================================================
<p class="text-left fragment" data-fragment-index="0">
  <b>Etapa 1 - Detecção da fonte</b>
</p>

<p class="text-left fragment" data-fragment-index="1">
  <b>Etapa 2 - Processamento iterativo (por janela)</b>
</p>

<ul>
  <li class="text-left fragment" data-fragment-index="2">
    (a) <b>Isolamento dos dados:</b> selecionar os dados magnéticos dentro da janela
  </li>
  <li class="text-left fragment" data-fragment-index="3">
    (b) <b>Deconvolução de Euler:</b> estimar a <em>posição</em> da fonte
  </li>
  <li class="text-left fragment" data-fragment-index="4">
    (c) <b>Inversão linear:</b> estimar o <em>momento</em> do dipolo usando posição fixa
  </li>

  <div style="display: grid;">
    <li class="text-left fragment fade-in-then-out" data-fragment-index="5" style="grid-area: 1/1; list-style: none;">
(d) <b>Inversão não linear:</b> refinar posição e momento via 
<a href="https://academic.oup.com/comjnl/article-abstract/7/4/308/354237?redirectedFrom=fulltext">Nelder-Mead</a>
</li>

<li class="text-left fragment fade-in" data-fragment-index="6" style="grid-area: 1/1; list-style: none;">
(d) <b>Inversão híbrida:</b> refinar posição e momento via 
<b>Levenberg-Marquardt</b>
</li>
  </div>

  <li class="text-left fragment" data-fragment-index="7">
    (e) <b>Remoção do sinal:</b> modelar o dipolo diretamente e subtrair do conjunto de dados completo
  </li>
</ul>

<p class="text-left fragment" data-fragment-index="8">
  <b>Etapa 3 - Repetir a detecção nos dados residuais:</b>
  aplicar as etapas 1 e 2 ao conjunto de dados residual
</p>

===============================================================================
# Sumário

<ul style="list-style: none">
  <li><b>Paleomagnetismo</b></li>
  <li><b>Microscopia magnética</b></li>
  <li>
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Fundamentação Teórica</li>
      <li  style="color: red !important;">Desenvolvimento de software</li>
    </ul>
  </li>
  <li><b>Comparação de Performance e Acurácia</b></li>  
  <li><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li><b>Conclusões</b></li>
</ul>

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/fatiando-website.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/documentation-home.png"  data-background-size="contain" data-background-color="#262626" -->


===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/documentation-api.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/documentation-function.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/documentation-tutorial.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/github.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/github_1.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/github_readme.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/pull_requests.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/pull_request_details.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/pull_request_details_1.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/pull_request_details_2.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
# Robustez e Pipeline de CI/CD
<div class="fragment text-left">

- **Integração Contínua (CI):** implementamos um pipeline automatizado que executa nossos de **testes de unidade** a cada *commit*, assegurando **100% de cobertura** das funções presentes no pacote

</div>

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/test.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================
# Distribuição e Ciência Aberta
<div class="fragment text-left">

- **Adotamos os pilares da Ciência Aberta**: desenvolvimento transparente no GitHub, issue tracking público e documentação completa com tutoriais replicáveis

</div>

<div class="fragment text-left">

- **Entrega contínua (CD):** facilitaremos o acesso global da nossa futura **versão v1.0** através dos gerenciadores padrão da comunidade científica:
  * **PyPI** (Python Package Index)
  * **conda-forge** (ambientes reprodutíveis)

</div>

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808f5" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/installing-conda.png"  data-background-size="contain" data-background-color="#080808f5" -->

===============================================================================
<!-- .slide: data-background-opacity="1" data-background-image="assets/checks.png"  data-background-size="contain" data-background-color="#262626" -->

===============================================================================




# Sumário
<ul style="list-style: none">
  <li><b>Paleomagnetismo</b></li>
  <li><b>Microscopia magnética</b></li>
  <li>
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Fundamentação Teórica</li>
      <li>Desenvolvimento de software</li>
    </ul>
  </li>
  <li style="color: red !important;"><b>Comparação de Performance e Acurácia</b></li>  
  <li><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li><b>Conclusões</b></li>
</ul>

===============================================================================
# Comparação de Performance e Acurácia
<div class="text-left">

- Avaliamos o **Magali** contra o algoritmo de inversão não-linear de **Souza-Junior et al. (2025)**.

</div>
<div class="fragment text-left">

- **Garantimos condições justas:** ambos os métodos partem da **mesma estimativa inicial** via Deconvolução de Euler ($\eta=3$) e o **nível de base é previamente removido**. Os métodos foram executados em um notebook de processador **Ryzen 3** com **8 Gb RAM**

</div>
<div class="fragment text-left">

- **Quantificamos** o desempenho em função do número de pontos de dados ($N$) realizando **5 inversões independentes** por resolução para obter medidas estáveis

</div>

===============================================================================
<div class="row">
<div class="col">

- Definimos dois cenários sintéticos com diferentes resoluções de malha ($\Delta \in [0.3, 2.0]~\mu\text{m}$):

1. **Modelo Simples:** Um único dipolo isolado

</div>

<div class="col-medium"><img src="assets/simple-model.png" style="width: 100%" >Espaçamento: $2 \mu m$</div>
</div>

===============================================================================
<div class="row">
<div class="col">

- Definimos dois cenários sintéticos com diferentes resoluções de malha ($\Delta \in [0.3, 2.0]~\mu\text{m}$):

1. **Modelo Simples:** Um único dipolo isolado

</div>

<div class="col-medium"><img src="assets/simple-model-1.png" style="width: 100%" > Espaçamento: $1 \mu m$</div>
</div>


===============================================================================
<div class="row">
<div class="col">

- Definimos dois cenários sintéticos com diferentes resoluções de malha ($\Delta \in [0.3, 2.0]~\mu\text{m}$):

1. **Modelo Simples:** Um único dipolo isolado

</div>

<div class="col-medium"><img src="assets/simple-model-2.png" style="width: 100%" > Espaçamento: $0.3 \mu m$</div>
</div>

===============================================================================
<div class="row">
<div class="col">

- Definimos dois cenários sintéticos com diferentes resoluções de malha ($\Delta \in [0.3, 2.0]~\mu\text{m}$):

1. **Modelo "Simple":** Um único dipolo isolado

2. **Modelo "1-Interf.":** Um dipolo alvo + uma fonte interferente próxima

</div>

<div class="col-medium"><img src="assets/one-interf.png" style="width: 100%"> Espaçamento: $2 \mu m$</div>
</div>

===============================================================================
<div class="row">
<div class="col">

- Definimos dois cenários sintéticos com diferentes resoluções de malha ($\Delta \in [0.3, 2.0]~\mu\text{m}$):

1. **Modelo "Simple":** Um único dipolo isolado

2. **Modelo "1-Interf.":** Um dipolo alvo + uma fonte interferente próxima

</div>

<div class="col-medium"><img src="assets/one-interf-1.png" style="width: 100%">Espaçamento: $1 \mu m$</div>
</div>


===============================================================================

<div class="row">
<div class="col">

- Definimos dois cenários sintéticos com diferentes resoluções de malha ($\Delta \in [0.3, 2.0]~\mu\text{m}$):

1. **Modelo "Simple":** Um único dipolo isolado

2. **Modelo "1-Interf.":** Um dipolo alvo + uma fonte interferente próxima

</div>

<div class="col-medium"><img src="assets/one-interf-2.png" style="width: 100%">Espaçamento: $0.3 \mu m$</div>
</div>


===============================================================================
<div class="row">
<div class="col">

- **Simple:** 

  - **Souza-Junior et al. (2025):** mantém um erro quase constante, menor que do **Magali** e abaixo de **0,2 μm**
  
  - **Magali:**  cresce conforme aumenta a densidade de dados e **estabiliza** em um erro de **~0,6 μm** para altas densidades de pontos

</div>
<div class="col-medium"><img src="assets/location-simple.png" style="width: 100%" ></div>
</div>


===============================================================================
<div class="row">
<div class="col">


- **1-Interf.:** 

  - **Souza-Junior et al. (2025):** mantém um erro quase constante pouco acima de **2 μm** 
 
  - **Magali:** melhora com o aumento de $N$, atingindo valores menores que **1 μm**

</div>
<div class="col-medium"><img src="assets/location-one-interf.png" style="width: 100%" ></div>
</div>

===============================================================================
<div class="row">
<div class="col">

- **Simple:** 
  - Magali tem um erro de intensidade muito próximo comparação a Souza-Junior et al. (2025), tendo ambos <br>~1$\times10^{-14}Am^2$

</div>
<div class="col-medium"><img src="assets/intensity_simple.png" style="width: 100%" ></div>
</div>


===============================================================================
<div class="row">
<div class="col">

- **1-Interf.:** 
  - Souza-Junior et al. (2025) apresenta um erro de intensidade de ~0.5$\times 10^{-14}Am^2$ 
  - Magali apresenta erro de intensidade de ~0.6$\times 10^{-14}Am^2$

</div>
<div class="col-medium"><img src="assets/intensity_one_interf.png" style="width: 100%" ></div>
</div>

===============================================================================

<div class="row">
<div class="col">

- **Souza-Junior et al. (2025):** tempo de execução **cresce linearmente** com o aumento do númeo de dados ($N$).

- **Magali:** mantém tempos de execução estáveis e abaixo de **0,5 segundos**.
</div>
<div class="col-medium"><img src="assets/execution_time_comparison.png" style="width: 100%" ></div>
</div>

===============================================================================
<div class="row">
<div class="col">

- **1-Interf.:** melhoria de aproximadamente **90%** para todos os números de dados

- **Simple:** melhoria quase sempre maior que **60%** superando **90%** em cenários com mais de **5.000 pontos**
</div>
<div class="col-medium"><img src="assets/percentage_of_improvement_execution_time.png" style="width: 100%" ></div>
</div>

===============================================================================
<div class="row">
<div class="col">

- **Simple:**
  - **Souza-Junior et al. (2025):** é constante a **~1 grau**

  - **Magali:** inicia a valor similar ao de Souza-Junior et al. (2025) e decai conforme a densidade de pontos aumenta atingindo **~0.4 grau**

</div>
<div class="col-medium"><img src="assets/angular_error_simple.png" style="width: 100%" ></div>
</div>

===============================================================================
<div class="row">
<div class="col">

- **1-Interf.:**
  - **Souza-Junior et al. (2025):**  permanece praticamente constante a **12 graus**, independentemente do volume de dados

  - **Magali:** diminui conforme $N$ aumenta, se aproximando a **6 graus**

</div>
<div class="col-medium"><img src="assets/angular_error_one_interf.png" style="width: 100%" ></div>
</div>

===============================================================================
<div class="row">
<div class="col">

- **Simple:** cresce conforme o número de pontos aumenta e estabiliza acima de **60%**

- **1-Interf.:** cresce conforme o número de pontos aumenta, atingindo valor **~45%**

</div>
<div class="col-medium"><img src="assets/percentage_of_improvement_angular_error.png" style="width: 100%" ></div>
</div>

===============================================================================
# Sumário

<ul style="list-style: none">
  <li><b>Paleomagnetismo</b></li>
  <li><b>Microscopia magnética</b></li>
  <li>
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Análise do Fluxo de Trabalho</li>
      <li>Fundamentação Teórica</li>
      <li>Desenvolvimento de software</li>
    </ul>
  </li>
  <li><b>Comparação de Performance e Acurácia</b></li>  
  <li  style="color: red !important;"><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li><b>Conclusões</b></li>
</ul>

===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->
<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
  }
  .block-space {
    margin-top: -1.0em !important;
  }
  .code {
    line-height: 0.2em;
  }
</style>
<pre class="compact"><code class="python" data-trim data-noescape>
  <span class="fragment code">import magali as mg</span>
  <span class="fragment code">import numpy as np</span>
  <span class="fragment code">import matplotlib.pyplot as plt</span>
  <span class="fragment code">import skimage.exposure</span>
  <span class="fragment code">import ensaio</span>
  <span class="fragment code">import harmonica as hm</span>
</code></pre>
</section>

===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->

<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
  }
  .block-space {
    margin-top: -1.0em !important;
  }
  .code {
    line-height: 0.2em;
  }
</style>
<pre class="compact"><code class="python" data-trim data-noescape>
<span class="fragment code">data_paths = {</span>
<span class="fragment code">    # Use o pacote Ensaio para buscar o conjunto de dados de espeleotema na internet</span>
<span class="fragment code">    "speleothem": ensaio.fetch_morroco_speleothem_qdm(</span>
<span class="fragment code">        version=1,</span>
<span class="fragment code">        file_format="matlab",</span>
<span class="fragment code">    ),</span>
<span class="fragment code">    "ceramic": "data/ceramic/NRM1.mat",</span>
<span class="fragment code">    "basalt": "data/basalt/NRM1.mat",</span>
<span class="fragment code">}</span>
</code></pre>
</section>


===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->

<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;    
  }
  .block-space {
    margin-top: -1.0em !important;
  }
  .code {
    line-height: 0.2em;
  }
</style>
<pre class="compact"><code class="python" data-trim data-noescape>
<span>
<span class="fragment code"># Processa cada conjunto de dados, mas utilizando parâmetros ligeiramente diferentes</span>
<span class="fragment code">size_ranges = {"speleothem": [20, 150], "ceramic": [10, 150], "basalt": [10, 30]}</span>
<span class="fragment code">detection_thresholds = {"speleothem": 0.02, "ceramic": 0.02, "basalt": 0.002}</span>
<span class="fragment code">datasets, locations, dipole_moments, bounding_boxes = {}, {}, {}, {}</span>
</code></pre>
</section>

===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->

<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment-code {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
    line-height: 0.2em;
  }
  .block-space {
    margin-top: -1.0em !important;
  }
  .code {
    line-height: 0.2em;
  }
</style>
<pre class="compact"><code class="python" data-trim data-noescape>
<span>
<span class="fragment code">for name in ["speleothem", "ceramic", "basalt"]:</span>
<span class="fragment code">    # Use o Magali para carregar os dados do formato de arquivo QDM Matlab de Harvard</span>
<span class="fragment code">    datasets[name] = mg.read_qdm_harvard(data_paths[name])
</code></pre>
</section>


===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->

<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
  }
  .block-space {
    margin-top: -1.0em !important;
  }
</style>
<pre class="compact"><code class="txt" data-trim data-noescape>
xarray.DataArray 'bz' (y: 600, x: 960)> Size: 5MB
array([[ 352.40587477,   94.8913792 ,   41.61924299, ...,  470.18833933,
         129.20055397,   18.50120941],
       [ 525.04809649,  624.84659897,   53.45418   , ...,  450.42515609,
         240.12455308,  -73.61367693],
       [ 105.0939369 ,  638.76559489,  307.60736872, ...,  236.91326522,
         386.8498122 ,  -86.44215589],
       ...,
       [ -83.74367957,   32.98078244, -411.75073652, ...,  745.99373583,
        1036.20033954, -140.64317643],
       [ 171.17113661, -214.47801235,  159.23437984, ...,  124.58138395,
         258.54331931,  -90.3376945 ],
       [  80.60950354,  273.08367487,  118.23499313, ...,   -4.19572521,
         -53.55728012,    2.10335918]])
Coordinates:
  * x        (x) float64 8kB 0.0 2.35 4.7 7.05 ... 2.249e+03 2.251e+03 2.254e+03
  * y        (y) float64 5kB 0.0 2.35 4.7 7.05 ... 1.403e+03 1.405e+03 1.408e+03
    z        (y, x) float64 5MB 5.0 5.0 5.0 5.0 5.0 5.0 ... 5.0 5.0 5.0 5.0 5.0
Attributes:
    long_name:  vertical magnetic field
    units:      nT
</code></pre>
</section>


===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->

<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment-code {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
    line-height: 0.2em;
  }
  .block-space {
    margin-top: -1.0em !important;
  }
  .code {
    line-height: 0.2em;
  }
</style>
<pre class="compact"><code class="python" data-trim data-noescape>
<span>
<span class="code">for name in ["speleothem", "ceramic", "basalt"]:</span>
<span style="margin-top: +0.5em !important;"  class="fragment code">    # Use o Magali para carregar os dados do formato de arquivo QDM Matlab de Harvard</span>
<span class="fragment code">    datasets[name] = mg.read_qdm_harvard(data_paths[name])</span>
<span class="fragment code">    # Continue os dados para cima em 5 micrômetros utilizando o pacote Harmonica</span>
<span class="fragment code">    height_difference = 5</span>
<span class="fragment code">    data_up = (</span>
<span class="fragment code">        hm.upward_continuation(datasets[name], height_difference)</span>
<span class="fragment code">        .assign_attrs(datasets[name].attrs)</span>
<span class="fragment code">        .assign_coords(x=datasets[name].x, y=datasets[name].y)</span>
<span class="fragment code">        .assign_coords(z=datasets[name].z + height_difference)</span>
<span class="fragment code">        .rename("bz")</span>
<span class="fragment code">    )</span>
<span class="fragment code">    # Calcule as derivadas dos dados e o TGA</span>
<span class="fragment code">    data_tga = mg.total_gradient_amplitude_grid(data_up)</span>
<span class="fragment code">    # Estique o contraste do TGA para destacar fontes fracas</span>
<span class="fragment code">    data_stretched = skimage.exposure.rescale_intensity(</span>
<span class="fragment code">        data_tga,</span>
<span class="fragment code">        in_range=tuple(np.percentile(data_tga, (1, 99))),</span>
<span class="fragment code">    )</span>
</code></pre>
</section>

===============================================================================
<!-- .slide: data-background-opacity="0" data-background-image="assets/installing-pip.png"  data-background-size="contain" data-background-color="#080808e6" -->

<section>
<style>
  pre.compact code {
    line-height: 1.0em !important;
    font-size: 1.3em !important;
  }
  .fragment {
    display: block;
    margin: 0 !important;
    padding: 0 !important;
    transform: none !important;
  }
  .block-space {
    margin-top: -1.0em !important;
  }
  .code {
    line-height: 0.2em;
  }
</style>
<pre class="compact"><code class="python" data-trim data-noescape>
<span>
<span class="fragment code">    # Use o LoG para detectar as fontes no TGA com contraste esticado</span>
<span class="fragment code">    bounding_boxes[name] = mg.detect_anomalies(</span>
<span class="fragment code">        data_stretched,</span>
<span class="fragment code">        size_range=size_ranges[name],  # μm</span>
<span class="fragment code">        detection_threshold=detection_thresholds[name],</span>
<span class="fragment code">        border_exclusion=2,</span>
<span class="fragment code">    )</span>
<span class="fragment code">    # Execute a inversão não linear para estimar os momentos dipolares e as localizações</span>
<span class="fragment code">    results = mg.iterative_nonlinear_inversion(</span>
<span class="fragment code">        data_up, bounding_boxes[name], copy_data=True</span>
<span class="fragment code">    )</span>
<span class="fragment code">    locations[name] = results[1]</span>
<span class="fragment code">    dipole_moments[name] = results[2]</span>
</code></pre>
</section>

===============================================================================
# Estalagmite
<img src="assets/result-speleothem.png" style="width: 100%" >
<div class="row">
<div class="col text-left small">

<div class="fragment">

- **57 possíveis fontes** detectadas
</div>


<div class="fragment">

- **Mineralogia e pulsos:** diferenciação de **hematita** (+Y) e **magnetita** (-Y) através de campos de pulso IRM (2.7 T e 0.3 T)
</div>

</div>

<div class="col text-left small">

<div class="fragment">

- **Baixa dispersão** de momentos estimados
</div>

</div>

</div>
<div class="footnote-center">

[Amostra e caracterização: Carmo et al. 2023](https://figshare.com/articles/dataset/QDM_magnetic_microscopy_dataset_of_a_speleothem_from_Morocco/22965200/1?file=40707380)
</div>

===============================================================================
# Fragmento de ladrilho cerâmico
<img src="assets/result-ceramic.png" style="width: 100%" >
<div class="row">
<div class="col text-left small">

<div class="fragment">

- **397 posíveis  fontes** detectadas
</div>

<div class="fragment">

- **Mineralogia:** **titanomagnetita** (SD/PSD) portadora da NRM em **assembleia estável e dispersa**
</div>
  
</div>

<div class="col text-left small">
<div class="fragment">

- Momentos estimados **razoavelmente concentados**
</div>

</div>

</div>
<div class="footnote-center">

[Amostra e caracterização: Poletti et al. (2016)](https://www.sciencedirect.com/science/article/pii/S0012821X16301625)
</div>

===============================================================================
# Rocha Basáltica
<img src="assets/result-basalt.png" style="width: 100%" >
<div class="row">
<div class="col text-left small">



<div class="fragment">

- **661 possíveis fontes** encontradas
</div>


<div class="fragment">

- **Mineralogia:** **magnetita** de baixo Ti ($10-50$ µm) com grãos SD, PSD e multidomínio (MD)</li>
</div>
</div>

<div class="col text-left small">


<div class="fragment">

- Região com **alta concentração** de anomalias sobrepostas
</div>

<div class="fragment">

- Momentos magnéticos estimados com **alta dispersão**
</div>
</div>
</div>
<div class="footnote-center">

[Amostra e caracterização: Moncinhatto et al. (2019)](https://academic.oup.com/gji/article/220/2/821/5603748)
</div>

===============================================================================
# Sumário

<ul style="list-style: none">
  <li><b>Paleomagnetismo</b></li>
  <li><b>Microscopia magnética</b></li>
  <li>
    <b>Métodos</b>
    <ul style="list-style: none">
      <li>Fundamentação Teórica</li>
      <li>Desenvolvimento de software</li>
    </ul>
  </li>
  <li><b>Comparação de Performance e Acurácia</b></li>  
  <li><b>Demonstração em dados reais de microscopia magnética</b></li>
  <li style="color: red !important;"><b>Conclusões</b></li>
</ul>

===============================================================================
<div class="text-left fragment">

- A **microscopia magnética** viabilizou o **paleomagnetismo** em escala de grão
</div>

<div class="text-left fragment">

- Códigos da literatura normalmente são desenvolvidos para o **escopo específico de cada artigo** e não seguem a práticas comuns de **reprodutibilidade**
</div>

<div class="text-left fragment">

- Não existe **software livre**, organizado e padronizado para inversão desses dados
</div>

<div class="fragment">

**Consequência:** dificuldade de comparação, validação e avanço coletivo
</div>

===============================================================================
<div class="quote">

Implementação do  **workflow completo** de Souza-Junior et al. (2025) com o avanço metodológico da **inversão híbrida** que  utiliza **derivadas analíticas**, evitando **normalização** e busca **extensiva**, em uma biblioteca **open-source**
</div>

===============================================================================

- Tempo de execução abaixo de 1 segundo e com ganho de **&gt; 90% de eficiência**

- Redução do erro angular **&gt; 60%** para o modelo simples e de **> 40%** para o modelo com interferência

===============================================================================
<div class="text-left">

- Projetamos para o **futuro** do Magali:

  <div class="fragment text-left">

  - Implementação de **expansão multipolar**

  </div>
  <div class="fragment text-left">

  - Módulos de **projeção estereográfica** e **filtragem** de inversão

  </div>
  <div class="fragment text-left">

  - Rotinas avançadas para **detecção automática** de fontes

  </div>
  <div class="fragment text-left">

  - Incluir Magali no **conda-forge** e **PyPi**

  </div>
  <div class="fragment text-left">

  - Melhorias na **documentação**

  </div>

  <div class="fragment text-left">

  - Release **V1.0**

  </div>
    <div class="fragment text-left">

  - **Difundir** o uso da biblioteca

  </div>

</div>

===============================================================================
<div class="quote">

**Magali** une **rigor matemático** e **ciência aberta** para consolidar o **paleomagnetismo de escala de grão** como uma técnica rápida, acessível e totalmente reprodutível

</div>

===============================================================================
# Agradecimentos

<img src="assets/capes.png" height=100%>


===============================================================================
<!-- .slide: data-background-opacity="0.2" data-background-image="assets/magali-logo.png"  data-background-size="contain" data-background-color="#262626" -->
# Obrigado!

<div class="row">
<div class="col">
<i class="fas fa-comments"></i>
<br>
Contato:
<a>yagomcastro1@gmail.com</a>

<i class="fab fa-github"></i>
<br>
Código-fonte desta apresentação:
<br>
[github.com/yagomcastro/msc-presentation-2026](https://github.com/yagomcastro/msc-presentation-2026)

<i class="fab fa-creative-commons"></i><i class="fab fa-creative-commons-by"></i>
<br>
O conteúdo desta apresentação está licenciado sob a
<br>
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)

</div>
<div class="col">

[github.com/fatiando/magali](https://github.com/fatiando/magali)

<img src="assets/qr_magali.gif" style="width: 80%" >
</div>
</div>

<img src="assets/qr_magali.gif" style="width: 0%" >
<div class="r-stretch centered">
<div>

