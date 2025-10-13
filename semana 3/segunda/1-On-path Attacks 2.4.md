Resumo do vídeo **On-path Attacks – CompTIA Security+ SY0-701 – 2.4**

---

Um **ataque on-path**, mais conhecido pelo seu nome em inglês, **Man-in-the-Middle (MitM)**, é uma técnica onde um invasor se posiciona secretamente no meio da comunicação entre dois dispositivos, como seu computador e um roteador de internet.

Pense nele como um carteiro mal-intencionado que intercepta suas cartas, lê o conteúdo, talvez até altere a mensagem, e depois as entrega ao destinatário. O mais perigoso é que, para você e para o destinatário, tudo parece perfeitamente normal. O ataque é **completamente invisível** para as vítimas.

---

### **Método 1: Envenenamento de ARP (ARP Poisoning)**

Este é um ataque MitM que acontece em uma **rede local** (como a rede Wi-Fi da sua casa ou do escritório), explorando uma fraqueza fundamental de um protocolo chamado **ARP (Address Resolution Protocol)**.

#### **A Fraqueza do ARP**

* **Função do ARP:** Em uma rede local, os dispositivos se comunicam usando um endereço físico de hardware chamado **endereço MAC**. O ARP é o protocolo responsável por "traduzir" um endereço IP (lógico, como `192.168.1.9`) para o seu endereço MAC correspondente (físico).
* **A Falha:** O ARP **não tem nenhum mecanismo de segurança**. Ele simplesmente confia em qualquer resposta que recebe.

#### **Como o "Veneno" Funciona**

1.  **Comunicação Normal:** Seu notebook (`IP 192.168.1.9`) precisa falar com o roteador (`IP 192.168.1.1`). Ele envia uma mensagem ARP para toda a rede perguntando: "Quem tem o IP `192.168.1.1`? Por favor, me envie seu endereço MAC". O roteador responde com seu MAC verdadeiro, e seu notebook guarda essa informação em uma tabela temporária (o **cache ARP**).

2.  **O Ataque:** O invasor, que está na mesma rede, começa a enviar mensagens ARP falsas e não solicitadas para o seu notebook. A mensagem diz: "Olá, o IP `192.168.1.1` (do roteador) agora pertence ao **meu** endereço MAC".

3.  **Envenenando o Cache:** Como o ARP é ingênuo, seu notebook acredita na mentira e atualiza seu cache. Agora, ele pensa que o endereço MAC do roteador é, na verdade, o endereço MAC do invasor.

4.  **Completando o Ataque:** O invasor faz o mesmo com o roteador, dizendo a ele que o MAC do seu notebook agora é o MAC do invasor.

**Resultado:** A partir desse momento, todo o tráfego entre seu notebook e o roteador passa primeiro pela máquina do invasor. Ele está "no meio" e pode ver, roubar ou modificar qualquer dado que não esteja fortemente criptografado.

---

### **Método 2: Ataque On-Path no Navegador (Man-in-the-Browser)**

Este é um tipo de ataque MitM ainda mais perigoso, pois o "homem no meio" não está na rede, mas sim **dentro do seu próprio computador**.

#### **Como Funciona?**

* **Infecção:** Um malware (como um Cavalo de Troia) infecta seu dispositivo e se instala como um "proxy" dentro do seu navegador ou sistema operacional.
* **A Grande Vantagem do Invasor:** Como o malware está rodando na sua máquina, ele consegue interceptar os dados **antes de serem criptografados** para serem enviados pela internet (por exemplo, quando você digita sua senha) e **depois de serem descriptografados** quando chegam do servidor.
* **Bypass da Criptografia:** Isso significa que mesmo o "cadeado de segurança" (HTTPS) do seu navegador não consegue te proteger, pois o malware captura as informações em texto plano, diretamente do seu computador.

#### **O Cenário de Risco: Acesso ao Banco**

O malware fica inativo, esperando você fazer algo importante, como acessar o site do seu banco.
1.  Você digita seu usuário e senha. O malware captura tudo imediatamente.
2.  Com suas credenciais, o malware pode iniciar outras sessões bancárias em segundo plano, sem que você perceba.
3.  Ele pode então realizar transferências, fazer compras ou roubar informações financeiras, tudo usando sua conta legítima.