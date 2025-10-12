Resumo do vídeo **Wireless Attacks – CompTIA Security+ SY0-701 – 2.4**

---

### **Ataque de Desautenticação Wi-Fi (Deauthentication Attack)**

Este ataque explora uma vulnerabilidade em como os dispositivos Wi-Fi se comunicam "nos bastidores" com o roteador (ou ponto de acesso).

#### **A Falha de Segurança: Os Frames de Gerenciamento**

Toda a comunicação para se conectar, manter a conexão e se desconectar de uma rede Wi-Fi é feita através de **frames de gerenciamento**. Eles são como mensagens de controle trocadas entre seu dispositivo e o roteador.

O grande problema é que, em padrões Wi-Fi mais antigos (anteriores ao `802.11ac`), esses frames **não eram criptografados**. Eles eram enviados em texto plano, ou seja, qualquer pessoa próxima poderia ver e manipular essas mensagens.



#### **Como o Ataque Funciona na Prática?**

1.  **Identificação:** O invasor usa uma ferramenta (como o `airodump-ng`) para "escutar" o tráfego da rede Wi-Fi e identificar o endereço de hardware (**endereço MAC**) do roteador e do dispositivo que ele quer atacar (a vítima).
2.  **Envio do Comando Falso:** O invasor usa outra ferramenta (como o `aireplay-ng`) para enviar um *frame de desautenticação* falsificado. Essa mensagem forjada parece vir do roteador e diz ao dispositivo da vítima: "desconecte-se agora".
3.  **Negação de Serviço:** O dispositivo da vítima obedece e se desconecta. O invasor pode continuar enviando esses frames em um loop, impedindo que a vítima consiga se reconectar à rede.

#### **A Solução: Padrões Wi-Fi Modernos**

Felizmente, essa falha foi corrigida. Padrões mais novos, como o **802.11ac (Wi-Fi 5)** e superiores (**Wi-Fi 6/6E**), implementaram uma proteção chamada **Protected Management Frames (PMF)**. Com essa tecnologia, os frames de gerenciamento críticos (como os de desautenticação) são **criptografados**, tornando esse tipo de ataque ineficaz em redes modernas e bem configuradas.

---

### **Jamming de Radiofrequência (RF Jamming)**

Enquanto o ataque de desautenticação explora uma falha no protocolo, o **jamming** ataca o meio físico: as ondas de rádio.

#### **O Que é? O Ataque do "Ruído"** 💥

O objetivo do jamming é **inundar a frequência do Wi-Fi com um sinal de interferência (ruído)**. Isso diminui drasticamente a **relação sinal-ruído**, que é a capacidade do seu dispositivo de "ouvir" o sinal do roteador em meio ao barulho do ambiente.

Se o ruído for muito alto, seu dispositivo não consegue mais entender os dados do roteador, e a comunicação se torna impossível para todos na área afetada.

* **Jamming Acidental:** Às vezes, isso acontece sem querer. Fornos de micro-ondas e lâmpadas fluorescentes antigas, por exemplo, podem causar interferência em redes de 2.4 GHz.
* **Jamming Malicioso:** Um invasor pode usar um transmissor para gerar ruído de propósito. As técnicas variam:
    * Transmitir um sinal constante e aleatório.
    * Transmitir um volume enorme de pacotes legítimos para congestionar a rede.
    * **Jamming Reativo:** Uma técnica mais sorrateira, onde o invasor só ativa o "ruído" quando detecta que alguém está tentando usar a rede, dificultando a identificação do problema.

#### **Como Encontrar o Invasor: A "Caça à Raposa" 🦊**

A boa notícia é que, para realizar um ataque de jamming, **o invasor precisa estar fisicamente próximo** do local. Encontrá-lo é um processo que operadores de rádio amador chamam de **"caça à raposa" (*fox hunt*)**.

Para isso, são usadas duas ferramentas principais:

1.  **Antena Direcional:** Permite apontar em diferentes direções para descobrir de onde o sinal de interferência está vindo mais forte.
2.  **Atenuador:** Quando se está muito perto da fonte, o sinal fica tão forte que é difícil saber a direção exata. O atenuador reduz a intensidade do sinal recebido, permitindo um ajuste fino para localizar o ponto exato do transmissor.



Usando essas técnicas, é possível triangular e encontrar a localização física do dispositivo que está causando o jamming na sua rede.