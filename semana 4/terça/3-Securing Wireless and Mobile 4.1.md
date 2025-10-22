Resumo do vídeo **Securing Wireless and Mobile – CompTIA Security+ SY0-701 – 4.1**

---

Esta aula aborda duas áreas principais: as ferramentas e técnicas usadas para analisar redes sem fio e as estratégias para gerenciar e proteger dispositivos móveis no ambiente corporativo.

#### **1. Site Survey de Redes Sem Fio (Wireless)**

Um "site survey" (análise de local) é realizado ao instalar ou solucionar problemas em uma rede Wi-Fi para entender o desempenho e a interferência de outras redes.

* **Objetivo:** Identificar todos os pontos de acesso (APs) próximos (seus e de vizinhos) para entender o espectro e escolher os melhores canais de frequência.
* **Frequência:** Deve ser refeito em intervalos regulares, pois o ambiente de RF (radiofrequência) muda constantemente com novos APs.
* **Ferramentas de Análise:**
    * **Mapas de Calor (Heat Maps):** A melhor forma de *visualizar* a cobertura. Cores quentes (vermelho/amarelo) indicam sinal forte; cores frias (azul) indicam sinal fraco.
    * **Ferramentas de Site Survey (ex: NetSpot):** Listam detalhes técnicos de todas as redes ao alcance (SSID, BSSID, canal, banda, força do sinal).
    * **Analisador de Espectro (Spectrum Analyzer):** Mais avançado que uma ferramenta de Wi-Fi. Ele mostra *todos* os sinais em uma frequência, incluindo interferências que *não são* Wi-Fi (ex: telefones sem fio, micro-ondas).

#### **2. Gerenciamento de Dispositivos Móveis (MDM)**

Um **MDM (Mobile Device Manager)** é uma plataforma centralizada para gerenciar os dispositivos móveis (smartphones, tablets) de uma organização.

* **Funções Principais:**
    * Implantar políticas de configuração.
    * Exigir a instalação de aplicativos específicos.
    * Gerenciar o uso de recursos (ex: desabilitar a câmera quando o funcionário está no escritório).
    * Aplicar políticas de segurança (ex: exigir bloqueio de tela, PIN ou senha).
* **Segmentação de Dados:** O MDM pode criar uma **partição de negócios** segura no dispositivo, mantendo os dados da empresa separados dos dados pessoais do usuário.

#### **3. Modelos de Propriedade de Dispositivos Móveis**

* **BYOD (Bring Your Own Device - Traga Seu Próprio Dispositivo):**
    * **Conceito:** O funcionário usa seu dispositivo pessoal para fins de trabalho.
    * **Desafio:** O dispositivo deve atender aos requisitos da empresa e ser gerenciado pelo MDM, garantindo a segurança dos dados corporativos e a privacidade dos dados do usuário. Exige políticas claras para quando o usuário troca ou vende o dispositivo (garantindo a limpeza dos dados).

* **COPE (Corporate Owned, Personally Enabled - De Propriedade Corporativa, Habilitado para Uso Pessoal):**
    * **Conceito:** A empresa compra e é dona do dispositivo, mas permite que o funcionário o utilize para fins pessoais (semelhante a um notebook corporativo).
    * **Vantagem:** O administrador tem controle total e pode apagar a partição de negócios sem afetar os dados pessoais do usuário.

* **CYOD (Choose Your Own Device - Escolha Seu Próprio Dispositivo):**
    * **Conceito:** Uma variação do COPE. O dispositivo ainda é de propriedade da empresa, mas o funcionário pode *escolher* seu modelo preferido dentro de uma lista pré-aprovada.

#### **4. Riscos de Segurança em Tecnologias Móveis**

* **Geral:** Dispositivos móveis são pequenos, fáceis de esconder, contêm muitos dados e podem estar em qualquer lugar do mundo.
* **Redes Celulares (4G/5G):** Os dados trafegam por redes que não controlamos.
    * **Riscos:** Monitoramento de tráfego, rastreamento de localização. Manter o dispositivo atualizado (patches) é crítico.
* **Redes Wi-Fi:**
    * **Riscos:**
        * Conectar-se a redes abertas/não criptografadas (ex: cafés, hotéis). A solução é sempre usar uma **VPN**.
        * "Eavesdropping" (escuta) por invasores na mesma área.
        * Ataques "On-path" (Man-in-the-Middle).
        * Ataques de Negação de Serviço (DoS) por interferência de RF.
* **Bluetooth (Rede de Área Pessoal - PAN):**
    * **Uso:** Conexão de curto alcance para acessórios (fones de ouvido, smartwatches).
    * **Risco:** Um dispositivo pareado pode ter acesso a dados no seu dispositivo.
    * **Defesa:** Usar o processo formal de **"pareamento" (pairing)** e nunca se conectar automaticamente a dispositivos Bluetooth desconhecidos.