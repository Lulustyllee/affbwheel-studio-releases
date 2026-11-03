# AFFBWheel Studio

Programa para Windows que configura um **volante com force feedback feito em casa** e os
acessórios dele para simuladores como o **Euro Truck Simulator 2**:

- **Volante** com FFB: Arduino Leonardo / Pro Micro, LOLIN S2 Mini (ESP32-S2) ou ESP32-S3, com
  gravação do firmware pelo próprio programa, giro, ganhos dos efeitos e resolução do encoder.
- **Pedal**: acelerador, freio e embreagem, com reconhecimento automático dos pinos e zonas mortas.
- **Dashboard**: telemetria do ETS2 para displays Arduino/ESP32, com instalação do plugin.
- **Aro**: display OLED no aro com menu de comandos do caminhão (freio de mão, farol, limpador,
  cruise…), confirmação pela telemetria, Bluetooth, botões e câmera pelo analógico.
- **ButtonBox**: cada pino da placa vira botão, chave, encoder, analógico ou atalho de teclado.

## Baixar e usar

1. Baixe o `.zip` mais recente em **[Releases](https://github.com/Lulustyllee/affbwheel-studio-releases/releases)**.
2. Extraia a pasta inteira (por exemplo em Documentos) e abra `AFFBWheel Studio.exe`.
   O programa não é assinado: se o Windows avisar "O Windows protegeu o computador", clique em
   **Mais informações → Executar assim mesmo**.
3. O `LEIA-ME.txt` dentro do zip tem os primeiros passos.

Não precisa instalar Python. Na primeira gravação de firmware o Studio baixa sozinho o Arduino CLI
e o suporte da placa (precisa de internet).

**Atualizações:** ao abrir, o Studio verifica se há versão nova. Se houver, aparece
**"● Nova versão …"** no rodapé da barra lateral; clique para ver as novidades e em
**Atualizar agora**. O Studio baixa, fecha, troca os arquivos e abre de novo. As configurações
ficam em `%LOCALAPPDATA%\AFFBWheelStudio` e não se perdem.

Requisitos: Windows 10 ou 11 de 64 bits. Bluetooth 4.0+ (BLE) só para os aparelhos sem fio.

## Feito com IA

Este software, os firmwares novos e a documentação foram **desenvolvidos com auxílio de
inteligência artificial** (Claude, da Anthropic, pelo Claude Code), a partir das ideias, dos
testes no hardware real e das decisões do autor. Revise as ligações elétricas antes de usar e
lembre que motores de force feedback têm força: **use por sua conta e risco**.

## Créditos

O firmware do volante é baseado no **[AFFBWheel](https://github.com/vsulako/AFFBWheel)**, de
**Sulako**, licença MIT, que por sua vez reúne o trabalho de:

- Tero Loimuneva (2012) e Saku Kekkonen (2013): descritores HID e tratamento dos relatórios de FFB;
- Jaka Simonic (2016): matemática do force feedback;
- Hoan Tran — hoantv (2019): Arduino-FFB-wheel.

As versões para ESP32-S2/S3, o protocolo Bluetooth e os firmwares do pedal, aro e ButtonBox
foram escritos para este projeto, seguindo a mesma base.

Também usa:

- **[scs-sdk-plugin](https://github.com/RenCloud/scs-sdk-plugin)** (RenCloud, a partir do
  trabalho de nlhans), licença MIT: plugin de telemetria do ETS2/ATS.
- **SCS Telemetry SDK**, da SCS Software.
- Python com **hidapi**, **pyserial** e **bleak**; empacotado com **PyInstaller**.
- **Arduino CLI**, núcleos **Arduino AVR** e **Espressif ESP32**, bibliotecas **Adafruit GFX**,
  **Adafruit SH110X/SSD1306** e **Adafruit BusIO**.
- **[vJoy](https://github.com/BrunnerInnovation/vJoy)** (opcional, para o joystick Bluetooth).

Os textos das licenças estão em `LICENCAS-TERCEIROS.txt`.
