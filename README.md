# Carro Autonomo

# - Introdução

  Nesse projeto será desenvolvido um protótipo de um carro autônomo capaz de se mover em uma faixa de trânsito fazendo uso de um controle de análise de terreno, localizando o centro de tais faixas. Na imagem abaixo podemos observar o protótipo.


![20170927_191015](https://user-images.githubusercontent.com/32318386/30941040-fc1fcd02-a3b9-11e7-84fc-f70cca70af30.jpg)


# - Reconhecimento da Pista

  O protótipo irá usar uma câmera de celular para fazer a captura de imagens no carro, essa câmera estará localiza aproximadamente 15cm acima do veículo para uma melhor captura do terreno. Na imagem é necessário que haja uma faixa de trânsito real ou simulada para que seja feito o processo de manipulação da imagem. Para o nosso projeto usaremos a seguinte pista para testes.
  
  
![20170927_201057](https://user-images.githubusercontent.com/32318386/30944976-dffa9cc0-a3d1-11e7-963c-8454d85211d3.jpg)


  Existem 4(quatro) passos principais que serão usados para a manipulação da imagem desejada, são esses: Captura da imagem, criação de thresholds binários, cálculo de curvatura da pista e detecção do centro da pista.


# - Manipulação das Imagens

  Nesse tópico buscaremos explicar de maneira geral os processos necessários para o reconhecimento da pista através de uma câmera de celular, o foco da explicação será o arquivo Get_Center.py.

1)  Durante a captura de imagem a câmera deve estar alinhada corretamente com as faixas desejadas;
  
2)  Na etapa de criação de thresholds binários iremos modificar a imagem em diferentes parâmetros, a biblioteca threshold_helpers.py possui diferentes ferramentas para a realização dessas funções, essas são:

      - abs_sobel_thresh(), calcula os limiares de cores entre os eixos X e Y afim de encontrar o melhor para o processamento da imagem;
      
      - hls_thresh(), faz uso da saturação HLS para modificação de cores;
      
      - hsv_thresh(). faz uso da saturação HSV para modificação de cores;
      
3)  Agora na detecção da curvatura da pista será criado um histograma para definir qual é o meio da faixa. No momento não será possível a postagem de imagens a respeito dessa etapa, porém é necessário entender que no programa esta etapa se inicia durante a função lr_curvature(binary_warped), após o termino desta etapa serão retornados os valores do centro da pista em forma de números.

4) Finalmente a detecção do centro da pista que será realizada com o auxílio do da detecção de curvatura, aqui também será mostrado através da contagem de pixels a distância em que o carro se encontra do centro da pista.

  Para melhor entendimento do processo veremos exemplos tanto do momento em que o thresh é aplicado assim como o resultado final nas imagens a seguir.
  
![figure_1-6](https://user-images.githubusercontent.com/32318386/30946109-67d9a950-a3d8-11e7-9121-dcc6b55a9248.png)

![figure_1-7](https://user-images.githubusercontent.com/32318386/30946108-64dd7e52-a3d8-11e7-9859-b147030feedb.png)

# - Considerações

  O projeto está em andamento e novas etapas e mais informações continuarão a ser atualizadas. Nos aprofundaremos no software e hardware utilizados no controle do protótipo, o controle PID e a programação no arduino, a comunicação serial ou bluetooth e mais modificações no projeto futuramente.

  
