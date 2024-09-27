# Reconhecimento de Gestos de Mão com OpenCV e MediaPipe

Este projeto implementa um sistema de reconhecimento de gestos de mão em tempo real usando **OpenCV** e **MediaPipe**. O sistema captura vídeo de uma webcam, detecta os pontos de referência das mãos e reconhece gestos específicos, como "Pare", "Joinha" e "OK". O projeto pode ser expandido para detectar mais gestos ou ser integrado a sistemas maiores que utilizam controle por gestos.

## Funcionalidades

- Detecção de mãos em tempo real usando a API de Mãos do MediaPipe.
- Reconhecimento de gestos específicos:
  - **Pare (Todos os dedos estendidos)**
  - **Joinha**
  - **OK (Polegar e dedo indicador formando um círculo)**
- Exibe feedback na tela para os gestos reconhecidos.
- Funciona com ambas as mãos (direita e esquerda).

  ## Como Funciona

1. **Captura de Vídeo**: O sistema usa a webcam como entrada (`cv2.VideoCapture`), capturando quadros em tempo real.
2. **Detecção de Mãos**: Usando a solução de Mãos do MediaPipe, detecta até duas mãos no quadro e identifica 21 pontos de referência em cada mão.
3. **Reconhecimento de Gestos**: Com base nas posições dos pontos de referência, o programa verifica três gestos específicos:
   - **Pare**: Todos os dedos estendidos.
   - **Joinha**: Apenas o polegar estendido para cima.
   - **OK**: Polegar e dedo indicador formando um círculo.
4. **Exibição**: O gesto reconhecido é exibido na tela, com rótulos indicando a mão detectada (direita ou esquerda) e o gesto correspondente.

## Visão Geral do Código

### Funções Principais

- **`verificar_sinal_pare(pontos)`**: Verifica se todos os dedos estão estendidos (gesto Pare).
- **`verificar_sinal_joinha(pontos)`**: Verifica se apenas o polegar está levantado (gesto Joinha).
- **`verificar_sinal_ok(pontos)`**: Detecta se o polegar e o dedo indicador formam um círculo (gesto OK).

### Bibliotecas Usadas

- **OpenCV**: Para captura de vídeo, manipulação de quadros e exibição de resultados.
- **MediaPipe**: Para detecção e rastreamento de pontos de referência das mãos.
