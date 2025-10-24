Resumo do vídeo **Asset Management – CompTIA Security+ SY0-701 – 4.2**

---

Esta aula aborda o ciclo de vida completo dos ativos de TI em uma organização, desde o processo formal de compra até o gerenciamento e, finalmente, o descarte seguro dos dados.

#### **1. O Processo de Aquisição (Purchasing Process)**

A compra de bens e serviços é um processo formal que envolve múltiplas aprovações.

* **Início:** Começa com a necessidade de um **usuário final** (ex: um novo software ou hardware).
* **Análise:** Envolve o grupo de TI e o departamento de **compras**. É preciso verificar o **orçamento** do departamento solicitante e obter aprovações formais (TI, Compras, Gerência).
* **Negociação:** Ocorre uma negociação com o fornecedor para garantir o melhor preço, termos de licenciamento e detalhes do contrato.
* **Compra e Pagamento:** O fornecedor entrega o produto/serviço e emite uma **fatura (invoice)**. Os termos de pagamento podem ser imediatos ou estendidos (ex: 30 ou 60 dias).

#### **2. Gerenciamento e Rastreamento de Ativos (Asset Tracking)**

Quando um produto tangível é recebido, ele deve ser inserido em um **sistema central de rastreamento de ativos** para gerenciar todo o seu ciclo de vida.

* **Propriedade (Ownership):** O ativo (ex: laptop) é formalmente atribuído a um usuário no sistema.
* **Classificação:** O sistema designa o tipo de dispositivo (laptop, desktop, etc.) e sua natureza:
    * **Hardware:** É considerado uma **Despesa de Capital (Capital Expenditure)**. Sofre depreciação ao longo do tempo, o que afeta os impostos.
    * **Software:** Geralmente é uma **Despesa Operacional (Operating Expense)**. Não sofre depreciação e é taxado de forma diferente.
* **Inventário e Help Desk:** O sistema é usado para inventariar componentes (laptops, roteadores, cabos). O Help Desk também o utiliza para popular tíquetes de suporte com o modelo exato do dispositivo do usuário.
* **Enumeração:** O sistema pode rastrear não apenas o ativo (ex: desktop), mas também seus componentes individuais (CPU, memória, HD, etc.).
* **Etiquetas de Ativo (Asset Tags):** Etiquetas físicas (com códigos de barras ou números) são afixadas aos dispositivos para identificação rápida e como um recurso de segurança contra perda ou roubo.

#### **3. Fim da Vida Útil: Sanitização e Destruição de Mídia**

Quando um dispositivo é reutilizado ou descartado, seus dados precisam ser tratados de forma segura.

* **Sanitização para Reutilização:**
    * **Objetivo:** Permitir que o dispositivo seja usado por outro funcionário.
    * **Método:** Usar um utilitário de **exclusão segura (secure delete)**. Isso garante que os dados antigos sejam *irrecuperáveis*, mas o drive permanece funcional.

* **Destruição Física (Para Descarte):**
    * **Objetivo:** Garantir que os dados *jamais* sejam vistos novamente.
    * **Métodos:**
        * **Triturador (Shredder) / Pulverizador:** Destrói fisicamente o drive.
        * **Perfuração/Martelamento:** Fazer furos nos pratos do HD (comum para poucos drives).
        * **Incinerar (Incineration):** Queimar os drives.
    * **Desmagnetização (Degaussing):**
        * Usa um campo eletromagnético poderoso para apagar os dados.
        * **Importante:** Este processo torna os discos rígidos (HDs) tradicionais completamente **inutilizáveis**.

* **Serviços de Terceiros e Certificação:**
    * Para grandes volumes (milhares de drives), empresas contratam especialistas em destruição.
    * Esse terceiro deve fornecer um **Certificado de Destruição (Certificate of Destruction)**, que é a confirmação legal de que os drives e os dados foram completamente destruídos.

#### **4. Retenção de Dados (Data Retention)**

O oposto da destruição é a **retenção de dados**, que define por quanto tempo as informações devem ser mantidas (incluindo originais, cópias e backups).

* **Motivos para Retenção:**
    * **Mandatos Legais/Regulatórios:** Leis que exigem que e-mails ou dados financeiros sejam guardados por um número específico de anos.
    * **Políticas Internas (Backup):** Guardar dados para recuperação em caso de exclusão acidental.
    * **Recuperação de Desastres (DR):** Ter os dados retidos disponíveis para restaurar as operações em um novo local.
* **Variedade:** Diferentes tipos de dados exigem diferentes períodos de retenção. É crucial ter políticas claras para cada tipo de informação.