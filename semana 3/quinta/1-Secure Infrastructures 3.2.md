Resumo do vídeo **Secure Infrastructures- CompTIA Security+ SY0-701 – 3.2**

---

### 1. A Natureza das Redes

Embora cada rede seja única (por exemplo, uma rede de **manufatura** é muito diferente de uma rede **médica**), os princípios fundamentais de segurança e os componentes básicos são muito semelhantes entre elas.

* **Firewalls:** São a ferramenta principal para **segmentar** a rede (dividi-la em partes) e controlar o tráfego, mantendo os invasores do lado de fora e permitindo a passagem de tráfego legítimo.
* **Outras Ferramentas:** A segurança não depende apenas de firewalls. Outros dispositivos ajudam a criar uma arquitetura segura, como:
    * **Honeypots:** "Armadilhas" projetadas para atrair e identificar invasores.
    * **Jump Servers:** Servidores de "pulo" seguros usados para acessar zonas críticas.
    * **Sensores de Rede:** Monitoram o tráfego em busca de atividades maliciosas.
    * **Load Balancers:** Distribuem o tráfego, o que também pode ajudar na segurança.

### 2. O Conceito de "Zonas de Segurança"

Uma das formas mais eficazes de projetar uma rede segura é usar **Zonas de Segurança**.

* **O que é?** É uma forma de **separação lógica** (não física) que agrupa dispositivos com base em seu **uso** ou **nível de acesso**, independentemente de suas faixas de IP ou sub-redes.
* **Exemplo Básico (Nomes):**
    * **Trusted Zone (Zona Confiável):** Geralmente a rede interna.
    * **Untrust Zone (Zona Não Confiável):** Geralmente a rede externa, como a Internet.
* **Exemplo Granular (Nomes Melhores):**
    Para uma segurança mais precisa, podemos criar múltiplas zonas:
    * **Inside (Interna):** A rede corporativa principal.
    * **Internet (Externa):** O mundo exterior.
    * **Servers (Servidores):** Onde ficam os servidores internos.
    * **Databases (Bancos de Dados):** Uma zona ainda mais restrita, apenas para os bancos de dados.
    * **Screened (ou DMZ):** Uma zona "peneirada" ou "desmilitarizada", onde ficam servidores que precisam ser acessados pela internet (como servidores web).

### 3. Zonas de Segurança na Prática (Regras de Firewall)

O uso de zonas torna as regras de firewall **mais fáceis de entender e manter**, mesmo em conjuntos de regras muito grandes.

* **Exemplos de Regras baseadas em Zonas:**
    1.  `PERMITIR` tráfego da `Zona Confiável` para a `Zona Não Confiável` (ex: usuários internos acessando a internet).
    2.  `PERMITIR` tráfego da `Zona Não Confiável` (Internet) para a `Zona "Screened"` (DMZ) (ex: clientes acessando seu servidor web).
    3.  `NEGAR` (ou permitir com muitas restrições) tráfego da `Zona Não Confiável` para a `Zona Confiável`.

### 4. Arquitetura de Rede com Zonas

* **Design Simples (2 Zonas):**
    Internet (`Zona Não Confiável`) $\rightarrow$ Firewall $\rightarrow$ Rede Interna (`Zona Confiável`)

* **Design Granular (3 Zonas):**
    Internet (`Zona Internet`) $\rightarrow$ Firewall $\rightarrow$ Servidores Web (`Zona Screened/DMZ`) $\rightarrow$ (Outro Firewall) $\rightarrow$ Rede Interna (`Zona Interna`)

Quanto maior a granularidade (mais zonas), mais **precisas** podem ser suas regras de segurança.

### 5. A Superfície de Ataque (Attack Surface)

* **O que é?** É a **soma de todas as aberturas e pontos fracos potenciais** que um invasor pode tentar explorar em sua rede.
* **Analogia:** Se sua rede fosse uma casa, a superfície de ataque seria todas as portas, janelas, porões e qualquer outra forma de entrar.
* **Pontos de Entrada na Rede (Vulnerabilidades):**
    * **Código de Aplicação:** Bugs ou falhas no software.
    * **Portas Abertas:** Serviços desnecessários rodando em um servidor.
    * **Autenticação:** Processos de login fracos.
    * **Erro Humano:** O fator mais perigoso; por exemplo, um administrador que configura incorretamente uma regra de firewall e acidentalmente deixa uma porta aberta.

### 6. Minimizando a Superfície de Ataque

O objetivo principal da segurança de rede é **minimizar o tamanho da superfície de ataque**.

* **Como fazer isso?**
    * **Auditar o código** das aplicações.
    * **Bloquear portas desnecessárias** no firewall (negar tudo por padrão).
    * **Monitorar o tráfego** em tempo real para ver quem está entrando e quais aplicações estão sendo usadas.

### 7. Protegendo a Própria Conectividade

A própria infraestrutura de cabos e conexões faz parte da superfície de ataque.

1.  **Proteção Física (Cabos):**
    * É crucial proteger fisicamente o cabeamento de rede.
    * Em muitos escritórios, os cabos ficam expostos ou os pontos de rede (nas mesas e salas de conferência) não têm proteção.
    * Deve-se proteger as "passagens" de cabos entre andares ou áreas.

2.  **Proteção Lógica (Criptografia):**
    * **O Risco:** Se um invasor conseguir se conectar fisicamente a um cabo ("grampear" a rede), ele poderá "ouvir" e capturar todo o tráfego que passa por ali.
    * **A Solução:** **Criptografia em nível de aplicação.**
    * **O Resultado:** Mesmo que o invasor capture os pacotes de dados, ele não conseguirá ler o conteúdo, pois estará criptografado.

3.  **Proteção de Acesso Remoto:**
    * Para locais remotos (como filiais) e usuários trabalhando de casa.
    * **Túneis IPsec:** Usados para criar uma conexão segura e criptografada de "site-a-site" (ex: matriz para filial).
    * **Concentrador VPN:** Equipamento que permite que usuários externos individuais se conectem de forma segura à rede corporativa.