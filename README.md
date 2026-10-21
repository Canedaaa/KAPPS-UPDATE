# KAPPS-UPDATE


Script em Node.js que modifica o **Kapps** já instalado, adicionando recursos novos e melhorando widgets existentes.

> Projeto não oficial, sem relação com os criadores do Kapps. Use por sua conta e risco.

## O que o patch adiciona

### Standings
- **Coluna de bandeira do país** de cada piloto (aparece nas colunas padrão, logo depois do nome). Pilotos sem país definido mostram um ícone de globo.
- **Correção da largura da janela do Standings** no overlay/OBS. Sem isso, a coluna da bandeira fazia a janela aparecer cortada ou sem poder ser redimensionada.
- **Correção no processo principal do Kapps**, que travava a abertura das janelas de uma layer quando a coluna da bandeira estava ativa.
- **SOF também em endurance / team racing**. O Kapps original só calcula o SOF quando não é corrida de equipe. Aqui ele usa a média de iRating dos pilotos de cada carro.

### Relatives
- **Bandeira do país** ao lado de cada piloto, com opção para ligar/desligar nas configurações.
- SOF também calculado em team racing.

### Fuel Calculator
- **Novo layout** em 4 colunas e 2 linhas: Fuel Level, Laps Remain, Fuel at End, PIT / Average, Last, L+1 e ADD.
- **Fuel at End**: combustível que sobra no fim da corrida. Na pista, mostra quanto vai sobrar (ou faltar, em negativo). No box, atualiza em tempo real enquanto você abastece.
- **ADD**: quanto abastecer para terminar a corrida, com as voltas restantes e o ritmo usado no cálculo.
- **Target laps (L+1)**: consumo por volta necessário para fazer uma volta a mais com o combustível atual. Há uma opção nas configurações para ligar/desligar.
- **Tempo perdido no box**: em corrida por tempo, o tempo da pit lane e da parada é descontado do tempo restante antes de contar as voltas. O valor é aprendido por pista a cada parada e guardado no navegador do Kapps. Na primeira parada de uma pista usa um valor padrão.

### Inputs Graph (visual novo)
- **Marcha e velocidade** em destaque, com unidade Auto (segue o iRacing), km/h ou mph.
- **Volante girando** com ângulo real. Você pode usar **seus próprios volantes**: crie uma pasta `wheels` ao lado do script com imagens PNG, SVG, JPG ou WEBP; cada arquivo vira uma opção nas configurações. Tamanho ajustável.
- **Barras de pedal** com o valor em % (embreagem, freio e acelerador).
- **ABS desenhado em cima da linha de freio**.
- **Dois estilos de layout** (Style 1 e Style 2, este com tudo dentro de um painel escuro de lado direito arredondado). Espaços, tamanhos e posições são ajustáveis no começo do script.

### Widgets novos ou substituídos
- **Weather** mostra Track, Air, Wind (com seta e bússola), Humidity, Wetness e Track State, com opções para mostrar/ocultar blocos e cor/opacidade do fundo.
- **PitBrake** balão de entrada no box com os estágios **WAIT, BRAKE e HOLD**, calculado pela telemetria.
- **Rejoin Helper** (aba nova): balão que aparece quando você sai da pista ou roda, mostrando o tempo até o carro mais próximo atrás de você. Fica verde (Clear), amarelo (Caution) ou vermelho (Danger), com limites ajustáveis nas configurações.
- **Twitch Chat** próprio (Twitch + YouTube) no lugar do original, com mensagens em balões separados, espaço entre balões ajustável e cor/opacidade do fundo.
- **Twitch Counters** próprio, mostrando os viewers do Twitch e do YouTube. Dá para exibir só uma plataforma ou as duas, e ajustar cor do fundo, opacidade, cantos, sombra e alinhamento.

### Pit Stop Helper
- **Pit Limiter independente**: o indicador LIMITER não depende mais da opção das barras de pit-lane, e fica no topo do widget, acima das barras.

### Configurações
- Abas originais **Standings (Legacy)** e **Pedals** removidas.
- Painéis do Racing Overlay **ordenados**: os ligados aparecem primeiro e os desligados depois.


## Como Instalar Do Zero
1. Atualize o Kapps para a ultima versão 1-24.40
2. extraia o zip e deixe-o na pasta doucumento
4. Feche o Kapps completamente.
5. Execute o arquivo aplicar atualização e de entrer no cmd
3. Abra o Kapps de novo.

## Como Instalar Caso Você Tenha Instalado um widget manualmente
1. Atualize o Kapps para a última versão 1-24.40
2. Feche o Kapps completamente.
3. Vá até C:\Users\Seu Usuario\AppData\Local\kapps\app-1.24.40\resources. apague o arquivo app.asar e renomeie app.asar.original-backup para app.asar
4. Execute o arquivo .bat aplicar atualização
3. Abra o Kapps de novo.
