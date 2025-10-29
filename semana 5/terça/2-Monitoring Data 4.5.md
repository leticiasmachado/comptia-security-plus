Resumo do vídeo **Monitoring Data – CompTIA Security+ SY0-701 – 4.5**

---

### 1. Monitoramento de Integridade de Arquivos (FIM)

#### O que é FIM?

Aplicações e servidores possuem dois tipos de arquivos:
1.  **Arquivos Estáticos:** Arquivos que raramente ou nunca deveriam mudar (executáveis, bibliotecas do sistema).
2.  **Arquivos Dinâmicos:** Arquivos que mudam constantemente (arquivos de dados, informações de cache).

Do ponto de vista da segurança, é crucial saber se os arquivos estáticos (que nunca deveriam mudar) estão sendo subitamente modificados. Um software de **Monitoramento de Integridade de Arquivos (FIM)** faz exatamente isso: monitora e alerta sobre quaisquer alterações nesses arquivos críticos.

#### Ferramentas de FIM

* **Windows:** O Windows possui o **System File Checker (SFC)**. Ele funciona sob demanda, escaneia todos os arquivos críticos do sistema operacional e, se encontrar um arquivo modificado ou corrompido, o substitui por uma versão boa conhecida.
* **Linux:** Uma ferramenta popular é o **Tripwire**. Ele também monitora mudanças em arquivos e pode fornecer monitoramento em tempo real para alertá-lo instantaneamente.
* **IPS Baseado em Host (HIPS):** Um Sistema de Prevenção de Intrusão (IPS) que roda no próprio sistema operacional (em vez de na rede) também pode realizar o monitoramento da integridade dos arquivos, pois tem acesso direto ao sistema de arquivos.

---

### 2. Prevenção contra Perda de Dados (DLP)

#### O que é DLP?

**Data Loss Prevention (DLP)**, ou Prevenção contra Perda de Dados, são sistemas projetados para identificar dados sensíveis que estão sendo enviados pela rede e bloquear esse tráfego em tempo real.

O objetivo é impedir que informações confidenciais (como números de CPF/Social Security, informações médicas, segredos comerciais) saiam da organização.

---

### 3. Os Três Estados dos Dados (Tipos de DLP)

As soluções de DLP atuam em três estados diferentes dos dados, dependendo de onde a monitoração ocorre:

| Estado do Dado | Descrição | Onde atua a solução de DLP |
| :--- | :--- | :--- |
| **Dados em Movimento (Data in Motion)** | Dados que estão sendo transferidos pela rede (ex: em um email ou upload). | **Nível da Rede.** A solução monitora os pacotes. Pode ser um appliance de rede dedicado ou um recurso integrado em um Firewall de Próxima Geração (NGFW). |
| **Dados em Uso (Data in Use)** | Dados que estão sendo ativamente processados na memória RAM de um computador. | **No Endpoint.** Também chamado de "Endpoint DLP", é um software instalado na estação de trabalho ou servidor que monitora a memória ativa. |
| **Dados em Repouso (Data at Rest)** | Dados que estão armazenados em um disco rígido ou sistema de arquivos. | **No Servidor/Armazenamento.** É um software que roda diretamente no servidor para escanear os arquivos armazenados. |

---

### 4. Aplicações Práticas e Vetores de Ameaça do DLP

#### 4.1. DLP no Endpoint e Controle de USB

Uma função comum do DLP de endpoint (Dados em Uso) é controlar o uso de periféricos, especialmente **unidades USB**.

* **Risco de Vazamento:** Dispositivos USB são pequenos, portáteis e facilitam a cópia e o roubo de grandes volumes de dados de forma discreta.
* **Risco de Infecção:** O USB também funciona na direção oposta. Um funcionário pode trazer um pendrive infectado de casa.
* **Exemplo (Caso do DoD):** Em novembro de 2008, no Departamento de Defesa dos EUA (DoD), alguém conectou um pendrive desconhecido em um sistema e, sem saber, lançou o worm `agent.btz`. O worm se replicou facilmente usando o armazenamento USB. Como resultado, o DoD baniu o uso de qualquer mídia flash ou dispositivo de armazenamento USB. Essas restrições foram suspensas em 2010 com novas diretrizes de uso.

#### 4.2. DLP na Nuvem (Cloud-based DLP)

À medida que as aplicações migram para a nuvem, as soluções de DLP também precisam estar lá.

* Funciona de forma similar a um appliance de rede, mas opera como um **appliance baseado na nuvem**.
* Ele monitora todo o tráfego que entra e sai de uma instância de aplicação na nuvem.
* Se alguém tentar transferir dados sensíveis para esse armazenamento em nuvem, o DLP na nuvem reconhecerá os dados e os **bloqueará antes que sejam armazenados**.
* Também pode bloquear outros tipos de tráfego, como malware e vírus.

#### 4.3. DLP de Email (O Vetor Mais Comum)

O email é um dos vetores de ameaça mais comuns para o vazamento de dados. Soluções de DLP de email existem tanto para servidores locais (on-premises) quanto para serviços em nuvem.

* **Análise de Entrada (Inbound):**
    * Procura por palavras-chave suspeitas.
    * Identifica emails falsificados (spoofed) ou de impostores.
    * Coloca esses emails em quarentena para que nunca cheguem à caixa de entrada do usuário.
* **Análise de Saída (Outbound):**
    * Bloqueia emails falsos de "transferência bancária".
    * Impede o envio de informações como formulários W-2 (que contêm números de Social Security).
    * Qualquer email de saída que pareça conter dados sensíveis pode ser bloqueado imediatamente.
* **Exemplo (Caso da Boeing):** Em novembro de 2016, um funcionário da Boeing enviou um email para seu cônjuge contendo uma planilha. A planilha parecia estar em branco, mas, na realidade, continha campos ocultos com informações pessoais (números de Social Security, datas de nascimento) de **36.000 funcionários** da Boeing. Uma solução de DLP de email teria analisado o anexo e bloqueado esse email. Ironicamente, a Boeing vende sua própria versão de software DLP, que não estava sendo usada nesse caso.