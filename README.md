# Instruções de uso

Para uso do software, siga os seguintes passos:

- **1°:** clone o repositório para o seu computador.

    - Ao abrir o projeto com o **VSCode**, a extensão do **CMake** irá criar a pasta ``build`` para você com os arquivos de compilação.

    - Caso não seja gerada a pasta, crie uma pasta com nome `build` e execute o seguinte comando dentro da pasta criada:
        
        ``cmake ..``

        O comando acima irá criar os arquivos de compilação.
        
        > Você pode também seguir para o passo 2 sem executar o passo anterior

- **2°:** execute a compilação do firmware usando a extensão do ***Raspberry Pi Pico*** do ***VSCode***.

A partir daqui, seu firmware já está compilado e pronto para uso, e só depende de onde será usado.

## Execução no ambiente de simulação Wokwi

Para utilizar o ***firmware*** no ambiente de simulação, basta ter a extensão do **Wokwi** instalado no seu ***VSCode***, além de ter configurado a sua licença.

Suprindo os requisitos citados acima, basta clicar no arquivo `diagram.json`, e a simulação já abrirá com o esquemático pronto.

***Clique no botão de play, no canto superior esquerdo e simule!***

## Execução na *BitDogLab*

Siga os passos a seguir para poder executar seu firmware na placa *BitDogLab*:

- **1°:** coloque o seu ***Raspberry*** em modo de ***bootsel***, clicando no botão branco na placa e reiniciando a mesma.

- **2°:** copie o arquivo `.uf2` que foi gerado na pasta `build` para o seu ***Raspberry*** (ele aparecerá como um armazenamento externo, um Pen-Drive com nome de RPI-RP2).

    - Após isso, o seu código já vai está rodando na sua plaquinha ***BitDogLab***.

- **3°:** Está pronto, dê os comandos para executar as funcionalidades clicando nas teclas do seu teclado.

## Instruções para uso do firmware

O firmware gerado faz o uso do pino 22 em configuração PWM para controle de um servomotor. Não faz uso de entrada nenhuma, sendo assim nenhuma ação é necessária, apenas visualize as saídas geradas.

O pino em configuração PWM gira a flange (braço) do servomotor de 0° a 180°. Inicialmente começa em uma rotina inicial, colocando por 5 segundos em 180°. Depois, mais 5 segundos em 90°. Após isso, aguarda mais 5 segundos em 0°. Depois da rotina inicial, o motor faz um giro suave de 0° a 180°, e de 180° a 0°, repetindo essa rotina enquando o dispositivo estiver ligado.

#### Teste com LED no lugar do servomotor

Um teste pode ser feito trocando o pino usado (22), pelo pino 12, pino conectado a LED azul do RGB LED presente na **BitDogLab**.

Ao fazer isso, pode-se observar a rotina inicial decrementando o brilho do led de 5 em 5 segundos. Logo após a rotina inicial, a outra rotina pode ser visualizada aumentando e diminuindo o brilho de forma gradativa e suave.

## Vídeo Ensaio

Clique em ***[link do video](https://drive.google.com/file/d/1qlz-bz6DcVHq5Py1jvXC1y7Pg3Kf6Me3/view?usp=sharing)*** para visualizar o vídeo ensaio do projeto.
