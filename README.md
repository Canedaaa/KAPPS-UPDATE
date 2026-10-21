<img width="1919" height="1079" alt="Captura de tela 2026-10-21 100128" src="https://github.com/user-attachments/assets/0aa0768d-3fe5-4659-bb69-dcc0e7cc4f01" />
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

================ENGLISH VERSION=================

A Node.js script that modifies an already installed **Kapps**, adding new features and improving existing widgets.

> Unofficial project, not affiliated with the creators of Kapps. Use at your own risk.

## What the patch adds

### Standings
- **Country flag column** for each driver (appears in the default columns, right after the name). Drivers without a country show a globe icon.
- **Standings window width fix** in the overlay/OBS. Without it, the flag column made the window appear cut off or impossible to resize.
- **Fix in the Kapps main process**, which crashed when opening a layer's windows while the flag column was active.
- **SOF also in endurance / team racing**. The original Kapps only calculates SOF when it is not a team race. Here it uses the average iRating of the drivers in each car.

### Relatives
- **Country flag** next to each driver, with an option to turn it on/off in the settings.
- SOF also calculated in team racing.

### Fuel Calculator
- **New layout** with 4 columns and 2 rows: Fuel Level, Laps Remain, Fuel at End, PIT / Average, Last, L+1 and ADD.
- **Fuel at End**: fuel left at the end of the race. On track, it shows how much will be left over (or missing, as a negative number). In the pits, it updates in real time while you refuel.
- **ADD**: how much to add to finish the race, with the remaining laps and the pace used in the calculation.
- **Target laps (L+1)**: fuel per lap needed to do one extra lap with the current fuel. There is an option in the settings to turn it on/off.
- **Time lost in the pits**: in timed races, the time spent in the pit lane and stopped is subtracted from the remaining time before counting laps. The value is learned per track at each stop and stored in the Kapps browser. On the first stop at a track, it uses a default value.

### Inputs Graph (new look)
- **Gear and speed** highlighted, with unit set to Auto (follows iRacing), km/h or mph.
- **Rotating steering wheel** with the real angle. You can use **your own wheels**: create a `wheels` folder next to the script with PNG, SVG, JPG or WEBP images; each file becomes an option in the settings. Adjustable size.
- **Pedal bars** with the value in % (clutch, brake and throttle).
- **ABS drawn on top of the brake line**.
- **Two layout styles** (Style 1 and Style 2, the latter with everything inside a dark panel with a rounded right side). Spacing, sizes and positions can be adjusted at the top of the script.

### New or replaced widgets
- **Weather** shows Track, Air, Wind (with arrow and compass), Humidity, Wetness and Track State, with options to show/hide blocks and background color/opacity.
- **PitBrake**: pit entry balloon with the **WAIT, BRAKE and HOLD** stages, calculated from telemetry.
- **Rejoin Helper** (new tab): a balloon that appears when you leave the track or spin, showing the time to the nearest car behind you. It turns green (Clear), yellow (Caution) or red (Danger), with adjustable thresholds in the settings.
- **Custom Twitch Chat** (Twitch + YouTube) replacing the original, with messages in separate bubbles, adjustable spacing between bubbles and background color/opacity.
- **Custom Twitch Counters**, showing Twitch and YouTube viewers. You can display just one platform or both, and adjust background color, opacity, corners, shadow and alignment.

### Pit Stop Helper
- **Independent Pit Limiter**: the LIMITER indicator no longer depends on the pit-lane bars option, and sits at the top of the widget, above the bars.

### Settings
- Original **Standings (Legacy)** and **Pedals** tabs removed.
- Racing Overlay panels **sorted**: enabled ones appear first and disabled ones after.

## How to Install From Scratch
1. Update Kapps to the latest version, 1.24.40.
2. Extract the zip and leave it in the Documents folder.
3. Close Kapps completely.
4. Open the file `aplicar atualização`.
5. Open Kapps again.

## How to Install If You Previously Installed a Widget Manually
1. Update Kapps to the latest version, 1.24.40.
2. Close Kapps completely.
3. Go to `C:\Users\Your User\AppData\Local\kapps\app-1.24.40\resources`. Delete the `app.asar` file and rename `app.asar.original-backup` to `app.asar`.
4. Open the file `aplicar atualização`.
5. Open Kapps again.
