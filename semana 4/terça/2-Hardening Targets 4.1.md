Resumo do vídeo **Hardening Targets – CompTIA Security+ SY0-701 – 4.1**

---

**"Hardening"** é o processo de aplicar configurações adicionais para aumentar a postura de segurança de um sistema. Fabricantes e a comunidade geralmente fornecem **"Guias de Hardening"** (hardening guides) para auxiliar nesse processo.

#### **1. Hardening de Dispositivos Móveis**

* **Patches:** Fabricantes liberam correções de bugs e atualizações de segurança. A aplicação desses patches fecha vulnerabilidades.
* **Segmentação de Dados:** Uma técnica comum é criar um segmento lógico para dados da empresa e outro para dados pessoais do usuário. Se um invasor acessar um segmento, ele não terá acesso ao outro.
* **Gerenciamento Centralizado:** Empresas usam um **MDM (Mobile Device Manager)** para monitorar dispositivos e implantar (push) atualizações de segurança em massa.

#### **2. Hardening de Estações de Trabalho (Workstations - Windows, macOS, Linux)**

* **Atualizações:** Patches periódicos são necessários para o SO, aplicações e até mesmo para o firmware do dispositivo.
* **Gerenciamento de Patches:** Muitas empresas compilam e liberam todos os patches de segurança em um dia específico do mês (ex: "Patch Tuesday" da Microsoft). Isso permite que o administrador de segurança teste todos de uma vez antes de implantar.
* **Remoção de Software:** Uma prática de segurança essencial é **remover qualquer software que não esteja sendo usado**. Cada software é uma potencial porta de entrada para vulnerabilidades.

#### **3. Hardening de Infraestrutura de Rede (Switches, Roteadores, Firewalls)**

* **Sistema Operacional (SO) Embarcado:** Esses dispositivos rodam um SO proprietário, específico para sua função (não Windows ou Linux), com acesso limitado.
* **Credenciais Padrão:** A prática mais importante é **sempre alterar as credenciais padrão** do administrador.
* **Autenticação:** Configurar autenticação, seja local ou centralizada (ex: RADIUS, TACACS+).
* **Patches:** As atualizações vêm *apenas* do fabricante e são raras. Por serem raras, quando uma atualização de segurança é liberada, ela é um evento importante e deve ser avaliada para implantação.

#### **4. Hardening de Servidores (Windows, Linux, etc.)**

* **Patches:** Aplicar todas as atualizações de segurança do SO e pacotes de serviço (service packs).
* **Autenticação:** Exigir complexidade e comprimento mínimo de senha.
* **Privilégio Mínimo:** Aplicar o princípio do menor privilégio a todas as contas e **desabilitar contas não utilizadas**.
* **Controle de Acesso:** Limitar quais dispositivos podem acessar o servidor, seja via firewall local (host) ou de rede.
* **Segurança de Endpoint:** Instalar soluções como **EDR (Endpoint Detection and Response)**, antivírus ou anti-malware.

#### **5. Hardening de Gerenciamento em Nuvem (Cloud)**

* **Estação de Trabalho de Gerenciamento:** O computador usado para administrar a nuvem deve ser extremamente seguro, pois tem acesso total.
* **Privilégio Mínimo:** Usar o console de gerenciamento para garantir que todos os serviços, redes e aplicações na nuvem tenham apenas as permissões mínimas necessárias para funcionar.
* **Monitoramento:** Instalar EDR nos sistemas baseados em nuvem.
* **Backup:** **Sempre ter um backup**, mesmo de sistemas em nuvem. Uma boa prática é fazer o backup para um *provedor de nuvem diferente*.

#### **6. Hardening de Sistemas Especializados**

* **SCADA / ICS (Sistemas de Controle Industrial):**
    * **Uso:** Monitora e controla equipamentos industriais em larga escala (ex: geração de energia, manufatura).
    * **Segurança:** São extremamente seguros. Frequentemente ficam em uma **rede isolada** ou até mesmo em **"air-gap"** (fisicamente desconectados) do resto da rede corporativa, sem acesso à internet.

* **Sistemas Embarcados (Embedded Systems):**
    * **Exemplos:** Smartwatches, TVs, eletrodomésticos inteligentes.
    * **Desafio:** O SO é limitado e as atualizações são raras e difíceis de aplicar.
    * **Ação:** Se um patch de segurança for liberado, deve ser instalado o mais rápido possível.
    * **Segurança:** Segmentar esses dispositivos em sua própria rede, preferencialmente protegida por um firewall.

* **RTOS (Sistema Operacional de Tempo Real):**
    * **Uso:** Sistemas onde o tempo de processamento é crítico e determinístico (ex: equipamentos militares, industriais, automotivos).
    * **Segurança:** Devem ser isolados da rede, rodar o mínimo de serviços necessários e, se precisarem de comunicação, usar um firewall.

* **IoT (Internet das Coisas):**
    * **Exemplos:** Sistemas de iluminação, aquecimento e refrigeração.
    * **Risco:** Fabricantes desses dispositivos geralmente não são especialistas em segurança.
    * **Segurança:**
        1.  Prioridade alta para patches de segurança.
        2.  **Segmentar** dispositivos IoT em sua própria rede para limitar o "raio de explosão" (blast radius) caso um dispositivo seja comprometido.