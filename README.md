# firmware
Após montar e conectar a sua impressora 3d Reprap Prusa Mendel, é hora de preparar o ambiente.

Vamos seguir as seguintes fontes:
http://andrewfinkle.com/news/2012/11/22/upgrading-ramps-14-to-marlin-firmware-prusa-mendel
https://reprap.org/wiki/Marlin

1ª Parte
Vamos usar o firmware Marlin, Arduino Mega e uma Ramps 1.2 de shield, além de quatro drivers pololo.
[traduzido do andrew finkle]
fazer o download de:
a. Consiste em printcore, pronsole e pronterface, e uma coleção de scripts auxiliares; coloque na pasta de aplicações
https://github.com/kliment/Printrun

b. Arduino IDE - O ambiente para editar código e fazer o upload para a placa i/o; coloque na pasta de aplicações
https://www.arduino.cc/en/Main/Software

c.Firmware Marlin - Uma mistura de Sprinter e grbl; a maior vantagem em relação ao Sprinter é a função Look Ahead (que mantem a velocidade da impressão a mais rápida possível); e é provável que se vocÊ comprar RAMPS montadas antes de 2012, ela veio instalada com Sprinter; faça o download do ZIP e descompacte num diretório conhecido.
https://github.com/ErikZalm/Marlin/
https://github.com/MarlinFirmware/Marlin

Observação:
Se essa é a primeira vez rodando essa impressora, talvez seja uma boa ideia checar se todo o hardware é operacional. Andrew Finkle encontrou esse script para testar tudo de maneira rápida e fácil. Irá mover o eixo X, Y, Z e E para frente e para trás e vai esquentar a cama aquecida e o hotend. Atenção: se você não quer testar o aquecimento da impressora, desconecte a cama aquecida e o hotend da sua placa.
https://reprap.org/wiki/File:RAMPS14_test.zip

2ª Parte
Abra a IDE Arduino. Plugue a RAMPS pela USB.
Agora conecte a placa ao software. Escolha no Tools > Serial Port > USB. O nome vai ser parecido com dev.tty.USB. Depois escolha Tools > Board > Arduino Mega 2560 ou Mega ADK.

3ª Parte
Edite o código do firmware Marlin para que ele seja equivalente ao seu setup de hardware.
No IDE Arduino, File > Open, navegue até o diretório do Marlin salvo anteriormente e abra o arquivo Marlin.pde (ou Marlin.ino).
Muitas abas serão abertas nesse momento, sendo que somente será necessário editar o texto das abas configuration.h e, eventualmente, o configuration_adv.h (para usuários avançados).
A seguir as adaptações necessárias para o funcionamento de uma Prusa Mendel v2, mas que pode ser entendida facilmente para outros modelos.





Como conecter os drives pololo na RAMPS 1.2:
https://reprap.org/wiki/RAMPS_1.2

Teoria sobre usar dois motores para movimentar dois eixos:
http://corexy.com/theory.html
