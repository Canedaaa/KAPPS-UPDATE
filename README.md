# KAPPS-UPDATE


Script em Node.js que modifica o **Kapps** já instalado, adicionando recursos novos e melhorando widgets existentes.

> Projeto não oficial, sem relação com os criadores do Kapps. Use por sua conta e risco.

## O que o patch adiciona

### Standings
<img width="628" height="1078" alt="Captura de tela 2026-10-20 224221" src="https://github.com/user-attachments/assets/eb995a70-9dd7-495f-ab6c-f9c9df1e80c5" />


- **Coluna de bandeira do país** de cada piloto (aparece nas colunas padrão, logo depois do nome). Pilotos sem país definido mostram um ícone de globo.
- **Correção da largura da janela do Standings** no overlay/OBS. Sem isso, a coluna da bandeira fazia a janela aparecer cortada ou sem poder ser redimensionada.
- **Correção no processo principal do Kapps**, que travava a abertura das janelas de uma layer quando a coluna da bandeira estava ativa.
- **SOF também em endurance / team racing**. O Kapps original só calcula o SOF quando não é corrida de equipe. Aqui ele usa a média de iRating dos pilotos de cada carro.

### Relatives
<img width="432" height="225" alt="Captura de tela 2026-10-21 154322" src="https://github.com/user-attachments/assets/118c7d30-d2ef-4860-9b15-7a8ce365a6b0" />


- **Bandeira do país** ao lado de cada piloto, com opção para ligar/desligar nas configurações.
- SOF também calculado em team racing.

### Fuel Calculator
<img width="373" height="112" alt="Captura de tela 2026-10-21 154751" src="https://github.com/user-attachments/assets/695f0b96-06bd-44dc-9af1-f9a4f22971aa" />


- **Novo layout** em 4 colunas e 2 linhas: Fuel Level, Laps Remain, Fuel at End, PIT / Average, Last, L+1 e ADD.
- **Fuel at End**: combustível que sobra no fim da corrida. Na pista, mostra quanto vai sobrar (ou faltar, em negativo). No box, atualiza em tempo real enquanto você abastece.
- **ADD**: quanto abastecer para terminar a corrida, com as voltas restantes e o ritmo usado no cálculo.
- **Target laps (L+1)**: consumo por volta necessário para fazer uma volta a mais com o combustível atual. Há uma opção nas configurações para ligar/desligar.
- **Tempo perdido no box**: em corrida por tempo, o tempo da pit lane e da parada é descontado do tempo restante antes de contar as voltas. O valor é aprendido por pista a cada parada e guardado no navegador do Kapps. Na primeira parada de uma pista usa um valor padrão.

### Inputs Graph (visual novo)
<img width="477" height="117" alt="Captura de tela 2026-10-21 154349" src="https://github.com/user-attachments/assets/69de11f3-9742-42fc-a5f6-071bcb57dd5c" />

- **Marcha e velocidade** em destaque, com unidade Auto (segue o iRacing), km/h ou mph.
- **Volante girando** com ângulo real. Você pode usar **seus próprios volantes**: crie uma pasta `wheels` ao lado do script com imagens PNG, SVG, JPG ou WEBP; cada arquivo vira uma opção nas configurações. Tamanho ajustável.
- **Barras de pedal** com o valor em % (embreagem, freio e acelerador).
- **ABS desenhado em cima da linha de freio**.
- **Dois estilos de layout** (Style 1 e Style 2, este com tudo dentro de um painel escuro de lado direito arredondado). Espaços, tamanhos e posições são ajustáveis no começo do script.

### Widgets novos ou substituídos
- **Weather** mostra Track, Air, Wind (com seta e bússola), Humidity, Wetness e Track State, com opções para mostrar/ocultar blocos e cor/opacidade do fundo.
 <img width="192" height="341" alt="Captura de tela 2026-10-21 154356" src="https://github.com/user-attachments/assets/40b6080e-a614-4406-95dd-26d92215575b" />

 
- **PitBrake** balão de entrada no box com os estágios **WAIT, BRAKE e HOLD**, calculado pela telemetria.

 <img width="268" height="155" alt="Captura de tela 2026-10-21 154945" src="https://github.com/user-attachments/assets/d2a52214-4501-4307-a95f-047ae5c9d98f" />
 
 <img width="217" height="110" alt="Captura de tela 2026-10-21 154959" src="https://github.com/user-attachments/assets/cba7e6ce-16e0-451f-9557-3781bc0a0b20" />
 
 <img width="225" height="118" alt="Captura de tela 2026-10-21 155006" src="https://github.com/user-attachments/assets/25380823-6722-4ddf-b810-cf608dfe99f0" />

 
- **Rejoin Helper** (aba nova): balão que aparece quando você sai da pista ou roda, mostrando o tempo até o carro mais próximo atrás de você. Fica verde (Clear), amarelo (Caution) ou vermelho (Danger), com limites ajustáveis nas configurações.
 <img width="529" height="195" alt="Captura de tela 2026-10-21 154318" src="https://github.com/user-attachments/assets/8237b1fe-8962-4405-8a28-c6d7e103d781" />

 
- **Twitch Chat** próprio (Twitch + YouTube) no lugar do original, com mensagens em balões separados, espaço entre balões ajustável e cor/opacidade do fundo.
 
 <img width="448" height="172" alt="Captura de tela 2026-10-21 154329" src="https://github.com/user-attachments/assets/9338dcc7-43c4-4865-8766-d9a56adbe6df" />

 
- **Twitch Counters** próprio, mostrando os viewers do Twitch e do YouTube. Dá para exibir só uma plataforma ou as duas, e ajustar cor do fundo, opacidade, cantos, sombra e alinhamento.
 
 <img width="127" height="56" alt="Captura de tela 2026-10-21 154333" src="https://github.com/user-attachments/assets/b8beba2a-c30d-47d3-87f4-40b78b9b40e9" />


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
<img width="628" height="1078" alt="Captura de tela 2026-10-20 224221" src="https://github.com/user-attachments/assets/eb995a70-9dd7-495f-ab6c-f9c9df1e80c5" />
- **Country flag column** for each driver (appears in the default columns, right after the name). Drivers without a country show a globe icon.
- **Standings window width fix** in the overlay/OBS. Without it, the flag column made the window appear cut off or impossible to resize.
- **Fix in the Kapps main process**, which crashed when opening a layer's windows while the flag column was active.
- **SOF also in endurance / team racing**. The original Kapps only calculates SOF when it is not a team race. Here it uses the average iRating of the drivers in each car.

### Relatives
<img width="432" height="225" alt="Captura de tela 2026-10-21 154322" src="https://github.com/user-attachments/assets/118c7d30-d2ef-4860-9b15-7a8ce365a6b0" />
- **Country flag** next to each driver, with an option to turn it on/off in the settings.
- SOF also calculated in team racing.

### Fuel Calculator
<img width="373" height="112" alt="Captura de tela 2026-10-21 154751" src="https://github.com/user-attachments/assets/695f0b96-06bd-44dc-9af1-f9a4f22971aa" />
- **New layout** with 4 columns and 2 rows: Fuel Level, Laps Remain, Fuel at End, PIT / Average, Last, L+1 and ADD.
- **Fuel at End**: fuel left at the end of the race. On track, it shows how much will be left over (or missing, as a negative number). In the pits, it updates in real time while you refuel.
- **ADD**: how much to add to finish the race, with the remaining laps and the pace used in the calculation.
- **Target laps (L+1)**: fuel per lap needed to do one extra lap with the current fuel. There is an option in the settings to turn it on/off.
- **Time lost in the pits**: in timed races, the time spent in the pit lane and stopped is subtracted from the remaining time before counting laps. The value is learned per track at each stop and stored in the Kapps browser. On the first stop at a track, it uses a default value.

### Inputs Graph (new look)
<img width="477" height="117" alt="Captura de tela 2026-10-21 154349" src="https://github.com/user-attachments/assets/69de11f3-9742-42fc-a5f6-071bcb57dd5c" />
- **Gear and speed** highlighted, with unit set to Auto (follows iRacing), km/h or mph.
- **Rotating steering wheel** with the real angle. You can use **your own wheels**: create a `wheels` folder next to the script with PNG, SVG, JPG or WEBP images; each file becomes an option in the settings. Adjustable size.
- **Pedal bars** with the value in % (clutch, brake and throttle).
- **ABS drawn on top of the brake line**.
- **Two layout styles** (Style 1 and Style 2, the latter with everything inside a dark panel with a rounded right side). Spacing, sizes and positions can be adjusted at the top of the script.

### New or replaced widgets
- **Weather** shows Track, Air, Wind (with arrow and compass), Humidity, Wetness and Track State, with options to show/hide blocks and background color/opacity.
  <img width="192" height="341" alt="Captura de tela 2026-10-21 154356" src="https://github.com/user-attachments/assets/40b6080e-a614-4406-95dd-26d92215575b" />
- **PitBrake**: pit entry balloon with the **WAIT, BRAKE and HOLD** stages, calculated from telemetry.
 <img width="268" height="155" alt="Captura de tela 2026-10-21 154945" src="https://github.com/user-attachments/assets/d2a52214-4501-4307-a95f-047ae5c9d98f" />
 <img width="217" height="110" alt="Captura de tela 2026-10-21 154959" src="https://github.com/user-attachments/assets/cba7e6ce-16e0-451f-9557-3781bc0a0b20" />
 <img width="225" height="118" alt="Captura de tela 2026-10-21 155006" src="https://github.com/user-attachments/assets/25380823-6722-4ddf-b810-cf608dfe99f0" />
- **Rejoin Helper** (new tab): a balloon that appears when you leave the track or spin, showing the time to the nearest car behind you. It turns green (Clear), yellow (Caution) or red (Danger), with adjustable thresholds in the settings.
 <img width="529" height="195" alt="Captura de tela 2026-10-21 154318" src="https://github.com/user-attachments/assets/8237b1fe-8962-4405-8a28-c6d7e103d781" />
- **Custom Twitch Chat** (Twitch + YouTube) replacing the original, with messages in separate bubbles, adjustable spacing between bubbles and background color/opacity.
 <img width="448" height="172" alt="Captura de tela 2026-10-21 154329" src="https://github.com/user-attachments/assets/9338dcc7-43c4-4865-8766-d9a56adbe6df" />
- **Custom Twitch Counters**, showing Twitch and YouTube viewers. You can display just one platform or both, and adjust background color, opacity, corners, shadow and alignment.
 <img width="127" height="56" alt="Captura de tela 2026-10-21 154333" src="https://github.com/user-attachments/assets/b8beba2a-c30d-47d3-87f4-40b78b9b40e9" />


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
