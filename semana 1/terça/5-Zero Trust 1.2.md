Resumo do vídeo **"Zero Trust - CompTIA Security+ SY0-701 - 1.2"** 

---

O modelo **Zero Trust** opera sob o princípio fundamental de **"Nunca Confie, Sempre Verifique"** (*Never Trust, Always Verify*).

Tradicionalmente, os sistemas de segurança confiavam implicitamente em qualquer entidade (usuário ou dispositivo) que estivesse dentro do perímetro da rede. O Zero Trust rejeita essa ideia. Ele assume que **qualquer tentativa de acesso** – vindo de dentro ou de fora da rede – pode ser uma ameaça e deve ser **explicitamente autenticada e autorizada** a cada vez que tenta acessar um recurso.

---

### 1. Planos de Operação (Functional Planes)

A segurança da rede é dividida para separar a gestão da execução:

* **Data Plane (Plano de Dados):** É responsável pelo **processamento ativo de dados** e tráfego da rede. É onde os dados circulam e as decisões de segurança são **aplicadas**.
* **Control Plane (Plano de Controle):** É o cérebro da arquitetura, onde as **políticas de segurança** e a **gestão de acesso** são configuradas e decididas.

### 2. Controles de Acesso e Identidade

* **Adaptive Identity (Identidade Adaptativa):** Consiste na análise da identidade do usuário com base em **variáveis contextuais** (como **localização**, **método de conexão** e **histórico de acesso**) para determinar e fortalecer continuamente o nível de autenticação necessário.
* **Zonas de Segurança (Security Zones):** Classificação das redes em zonas **confiáveis** e **não confiáveis** para restringir o acesso com base na origem da conexão. Permite um controle de acesso mais granular.

### 3. Mecanismos de Aplicação de Políticas

* **Policy Enforcement Point (PEP):** Atua como um **"gatekeeper"** (porteiro). Ele é o ponto de controle que inspeciona o tráfego de rede e assegura que as políticas de segurança sejam seguidas. O PEP notifica o ponto de decisão de políticas (PDP) para obter autorização antes de conceder acesso.

---

### Princípios e Implementação

O modelo Zero Trust é construído sobre os seguintes conceitos:

1.  **Verificação Contínua:**
    * Cada usuário, dispositivo e processo deve ser **autenticado** e **autorizado** a cada solicitação de acesso a um recurso, independentemente de onde estejam.
    * Isso geralmente envolve o uso de **Autenticação Multifator (MFA)**.

2.  **Acesso de Menos Privilégio (*Least-Privilege Access*):**
    * Os usuários e sistemas só recebem o **nível mínimo de acesso** necessário para realizar sua tarefa imediata.
    * Isso limita o movimento lateral (lateral movement) de um invasor caso uma conta seja comprometida.

3.  **Microsegmentação:**
    * A rede é dividida em **pequenas zonas de segurança** e segmentos, com políticas de acesso estritas entre eles. Isso garante que, se um invasor entrar em um segmento, ele não terá acesso automático a toda a rede.

4.  **Identidade Adaptável (*Adaptive Identity*):**
    * O sistema avalia o **contexto** da tentativa de acesso em tempo real, examinando fatores de risco além das credenciais básicas, como:
        * **Localização** (país, cidade, etc.).
        * **Tipo de conexão** (VPN, interna, etc.).
        * **Saúde e conformidade do dispositivo** (se está com o software atualizado).
        * Se o usuário está tentando acessar recursos incomuns para seu cargo.
    * Se o risco for alto, o sistema pode exigir uma **autenticação adicional**.

### Componentes da Arquitetura Zero Trust

A arquitetura é dividida em planos (ou *Planes of Operation*) que separam o tráfego de dados da lógica de decisão:

* **Plano de Dados (*Data Plane*):** Lida com o tráfego real da rede, como frames e pacotes. É o ponto onde as regras de segurança são **aplicadas**.
* **Plano de Controle (*Control Plane*):** É onde as **decisões de política** são tomadas. Inclui os seguintes elementos:
    * **Ponto de Aplicação de Política (*Policy Enforcement Point* - PEP):** O "porteiro" que recebe o tráfego e consulta o Plano de Controle. É ele que **executa** a decisão de acesso (permitir/negar).
    * **Mecanismo de Política (*Policy Engine*):** Analisa todos os dados contextuais e define a decisão de acesso.
    * **Administrador de Política (*Policy Administrator*):** Responsável por criar credenciais ou *tokens* de acesso e comunicá-los ao PEP, autorizando o acesso após a decisão do Mecanismo de Política.Aqui está o resumo do modelo Zero Trust com as redundâncias removidas e o conteúdo reorganizado de forma mais concisa.

---

## Resumo do Modelo Zero Trust (CompTIA Security+ SY0-701)

O modelo **Zero Trust** (Confiança Zero) é uma arquitetura de segurança baseada no princípio fundamental: **"Nunca Confie, Sempre Verifique"** (*Never Trust, Always Verify*).

Ele rejeita a confiança implícita no perímetro da rede, assumindo que **qualquer tentativa de acesso** (interna ou externa) é uma ameaça em potencial e deve ser **explicitamente autenticada e autorizada** a cada solicitação de recurso.

---

### 1. Princípios de Implementação

O modelo é sustentado por controles rigorosos:

* **Verificação Contínua:** Cada usuário, dispositivo e processo deve ser **autenticado** a cada solicitação.
    * Exige o uso frequente de **Autenticação Multifator (MFA)**.
* **Acesso de Menos Privilégio (*Least-Privilege Access*):** Usuários e sistemas recebem apenas o **nível mínimo de acesso** estritamente necessário para sua função.
* **Microsegmentação:** A rede é dividida em **pequenas zonas de segurança** com políticas de acesso estritas entre elas, limitando o **movimento lateral** de invasores.

### 2. Controles de Acesso e Contexto

* **Identidade Adaptativa (*Adaptive Identity*):** O sistema avalia o **contexto** da tentativa de acesso em tempo real, examinando fatores de risco como **localização**, **tipo de conexão** e **saúde do dispositivo**, podendo exigir autenticação adicional se o risco for alto.
* **Zonas de Segurança (*Security Zones*):** Classificação da rede em zonas **confiáveis** e **não confiáveis** para restringir o acesso com base na origem da conexão, garantindo um controle mais granular.

### 3. Componentes da Arquitetura (Planes of Operation)

A arquitetura Zero Trust divide as operações de rede em planos funcionais:

| Componente | Função Principal |
| :--- | :--- |
| **Data Plane** (Plano de Dados) | Processa o **tráfego de dados** real (frames, pacotes). É onde as decisões de segurança são **executadas**. |
| **Control Plane** (Plano de Controle) | Onde as **políticas de segurança** e as decisões de acesso são gerenciadas. |
| **Policy Enforcement Point (PEP)** | O **"gatekeeper"** que inspeciona o tráfego e executa a decisão de acesso (permitir/negar), consultando o Plano de Controle. |
| **Mecanismo de Política** | Analisa os dados contextuais e define a **decisão de acesso**. |
| **Administrador de Política** | Cria e comunica as credenciais de acesso (*tokens*) ao PEP. |