# Carro Autonomo

# - Introdução

  Nesse projeto será desenvolvido um protótipo de um carro autônomo capaz de se mover em uma faixa de trânsito fazendo uso de um controle de análise de terreno, localizando o centro de tais faixas. Na imagem abaixo podemos observar o protótipo.


![20170927_191015](https://user-images.githubusercontent.com/32318386/30941040-fc1fcd02-a3b9-11e7-84fc-f70cca70af30.jpg)


# - Reconhecimento da Pista

  O protótipo irá usar uma câmera de celular para fazer a captura de imagens no carro, essa câmera estará localiza aproximadamente 15cm acima do veículo para uma melhor captura do terreno. Na imagem é necessário que haja uma faixa de trânsito real ou simulada para que seja feito o processo de manipulação da imagem. Para o nosso projeto usaremos a seguinte pista para testes.
  
  
![20170927_201057](https://user-images.githubusercontent.com/32318386/30944976-dffa9cc0-a3d1-11e7-963c-8454d85211d3.jpg)


  Existem 4(quatro) passos principais que serão usados para a manipulação da imagem desejada, são esses: Captura da imagem, criação de thresholds binários, cálculo de curvatura da pista e detecção do centro da pista.


# - Manipulação das Imagens

1)  Durante a captura de imagem a câmera deve estar alinhada corretamente com as faixas desejadas;
  
2)  Na etapa de criação de thresholds binários iremos modificar a imagem em diferentes parâmetros, a biblioteca threshold_helpers.py possui diferentes ferramentas para a realização dessas funções, essas são:

      - abs_sobel_thresh(), calcula os limiares de cores entre os eixos X e Y afim de encontrar o melhor para o processamento da imagem;
      
      - hls_thresh(), faz uso da saturação HLS para modificação de cores;
      
      - hsv_thresh(). faz uso da saturação HSV para modificação de cores;
  
