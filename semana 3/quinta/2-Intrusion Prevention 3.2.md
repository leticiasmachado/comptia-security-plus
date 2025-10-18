Resumo do vídeo **Intrusion Prevention – CompTIA Security+ SY0-701 – 3.2**

---

### 1. IPS vs. IDS: A Diferença Fundamental

Ambos os sistemas analisam o tráfego de rede em busca de ameaças, mas sua ação é o que os diferencia.

* **IPS (Intrusion Prevention System - Sistema de Prevenção de Intrusão):**
    * **Ação:** É um sistema **ativo**. Ele observa o tráfego em tempo real e, se detectar algo malicioso (um exploit conhecido, uma injeção de SQL, um buffer overflow), ele pode **BLOQUEAR** a ameaça imediatamente, impedindo que ela chegue ao seu destino.

* **IDS (Intrusion Detection System - Sistema de Detecção de Intrusão):**
    * **Ação:** É um sistema **passivo**. Ele também observa e identifica ameaças, mas sua única função é **GERAR UM ALERTA**. Ele pode te avisar sobre o perigo, mas **NÃO PODE** bloquear o tráfego.

Em resumo: o **IPS previne (bloqueia)**, enquanto o **IDS apenas detecta (alerta)**.

### 2. O Desafio dos Dispositivos "Inline": Modos de Falha

Dispositivos de segurança como o IPS são frequentemente colocados "inline", ou seja, diretamente no caminho do tráfego de rede. Isso cria uma questão crítica: **o que acontece com o tráfego se o IPS falhar** (por perda de energia, problema de hardware ou bug de software)?

Existem dois comportamentos possíveis:

1.  **Fail-Open (Falha Aberta):**
    * **Comportamento:** Se o dispositivo falhar, ele se torna uma "ponte aberta". O tráfego **continua a fluir** através dele sem interrupção.
    * **Vantagem:** A rede permanece funcional; não há downtime.
    * **Desvantagem:** Durante a falha, **nenhuma segurança é aplicada**. O tráfego passa sem ser inspecionado.

2.  **Fail-Closed (Falha Fechada):**
    * **Comportamento:** Se o dispositivo falhar, ele se torna uma "parede". O link de rede é **cortado** e nenhum tráfego pode passar.
    * **Vantagem:** Garante a segurança máxima. Nenhum dado passa sem inspeção, mesmo durante uma falha.
    * **Desvantagem:** Causa **downtime imediato** na rede. A comunicação para completamente.

A maioria das redes prefere uma configuração **fail-open** para garantir a continuidade, mas isso depende do nível de segurança exigido. É crucial verificar a documentação do seu equipamento para saber qual é o seu comportamento padrão.

### 3. Monitoramento Ativo (Configuração Inline)

Este é o modo de operação padrão para um IPS, projetado para bloquear ameaças em tempo real.

* **Arquitetura:** O IPS é colocado **diretamente no caminho do tráfego**, por exemplo, entre o firewall e o switch principal da rede.
* **Fluxo do Tráfego:**
    Internet $\rightarrow$ Firewall $\rightarrow$ **IPS** $\rightarrow$ Switch Principal
* **Como Funciona:** Todo o tráfego que passa pelo link *deve* atravessar o IPS. O IPS examina cada pacote, decide se é legítimo ou malicioso e, se for malicioso, **descarta o pacote imediatamente**, impedindo que ele continue.
* **Vantagens:**
    * Bloqueio de ameaças em tempo real. É a forma mais eficaz de prevenção.
* **Preocupações (Desvantagens):**
    * **Downtime:** Se o IPS falhar (e for fail-closed), ele pode derrubar a rede.
    * **Falsos Positivos:** Existe o risco de o IPS ser "agressivo demais" e bloquear tráfego legítimo por engano, causando problemas para os usuários.

### 4. Monitoramento Passivo (Configuração Fora de Banda)

Devido às preocupações com o monitoramento ativo, algumas organizações preferem uma abordagem passiva.

* **Arquitetura:** O IPS **NÃO** é colocado no caminho do tráfego. Em vez disso, ele é conectado a uma porta especial no switch, que envia a ele uma **CÓPIA** de todo o tráfego.
* **Fluxo do Tráfego:**
    * **Caminho Original:** Firewall $\leftrightarrow$ Switch Principal $\leftrightarrow$ Dispositivos
    * **Caminho da Cópia:** Switch Principal $\rightarrow$ **IPS**
* **Como Funciona:** O tráfego flui normalmente entre os dispositivos. O switch duplica os pacotes e envia uma cópia para o IPS para análise.
* **Vantagens:**
    * **Sem Downtime:** Como o IPS não está no caminho principal, uma falha nele não afeta a rede de forma alguma.
* **Desvantagens:**
    * **Capacidade de Bloqueio Limitada:** Como o IPS está analisando apenas uma cópia, o tráfego malicioso original **já chegou (ou está a caminho) do seu destino**. Ele pode identificar e alertar sobre o ataque, mas não pode impedi-lo em tempo real.
    * **Função de IDS:** Mesmo usando um equipamento IPS, essa configuração funciona essencialmente como um **IDS**, pois seu papel principal se torna a detecção e o alerta.

### 5. Como o Monitoramento Passivo Obtém o Tráfego?

Para que o monitoramento passivo funcione, o IPS precisa receber uma cópia do tráfego. Isso é feito de duas maneiras principais:

1.  **Port Mirror / SPAN (Switch Port Analyzer):**
    * É uma **funcionalidade do próprio switch**. Você configura o switch para "espelhar" (copiar) todo o tráfego que passa por uma ou mais portas (ou uma VLAN inteira) e enviá-lo para uma porta de destino, onde o IPS está conectado.

2.  **Network Tap (Derivador de Rede):**
    * É um **dispositivo de hardware** que é fisicamente inserido em um cabo de rede. Ele intercepta o sinal e cria duas saídas idênticas: uma que continua o caminho original e outra que vai para o dispositivo de monitoramento (o IPS).