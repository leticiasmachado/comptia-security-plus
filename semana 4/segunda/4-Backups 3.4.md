Resumo do vídeo **Backups – CompTIA Security+ SY0-701 – 3.4**

---

#### **1. Planejamento de Backup (Variáveis de Configuração)**

Antes de implementar uma estratégia, é preciso responder a várias perguntas-chave:

* **Volume de Dados:** Quanto dado precisa ser copiado (Megabytes, Terabytes, etc.)?
* **Tipo de Backup:** Qual método será usado (completo, incremental, etc.)?
* **Mídia de Backup:** Onde os dados serão salvos (Fita, HD local, Nuvem)?
* **Local de Armazenamento:** Onde a mídia de backup ficará guardada?
    * **On-site (Local):** No mesmo local da fonte de dados.
    * **Off-site (Externo):** Em um local físico diferente ou na nuvem.
* **Software:** Qual software será usado para fazer o backup e, mais importante, para a restauração?
* **Cronograma:** Com que frequência os backups serão executados (Diário, semanal, mensal)?

#### **2. Localização: On-site vs. Off-site**

* **Backup On-site (Local):**
    * **Definição:** Os dados e a mídia de backup estão localizados no mesmo prédio/site.
    * **Vantagens:** Acesso imediato, restauração muito rápida (não depende de links externos), geralmente mais barato.
    * **Desvantagem:** Vulnerável a desastres locais (incêndio, inundação).

* **Backup Off-site (Externo):**
    * **Definição:** Os dados são transferidos (via rede ou fisicamente, ex: fitas) para um local diferente (outro prédio, um cofre terceirizado ou a nuvem).
    * **Vantagens:** Protege contra desastres locais. Permite a restauração dos dados mesmo que o site principal seja perdido.
    * **Estratégia Comum:** Muitas organizações usam ambos: *on-site* para recuperação rápida de arquivos e *off-site* para recuperação de desastres (DR) e armazenamento de longo prazo.

#### **3. Agendamento e Intervalos (Quando fazer o backup?)**

A frequência do backup (diária, semanal, horária) depende da criticidade e da taxa de alteração dos dados. É comum criar "conjuntos de backup" (backup sets) com intervalos diferentes.

* **Exemplo:**
    * **Conjunto Diário:** 30 backups são retidos por mês.
    * **Conjunto Semanal:** 4 backups são retidos por mês.
    * **Conjunto Mensal:** 12 backups são retidos por ano.

#### **4. Segurança dos Backups (Protegendo a Cópia)**

Os backups contêm todos os dados sensíveis da organização e são um alvo de alto valor.

* **Risco Físico:** Houve casos reais de fitas de backup roubadas de veículos durante o transporte para um local off-site.
* **Solução: Criptografia:**
    * Todos os dados devem ser **criptografados** antes de serem gravados na mídia ou transferidos.
    * Se a mídia for roubada, os dados estarão ilegíveis.
    * **Ponto Crítico:** É vital ter um plano de gerenciamento seguro para as chaves de descriptografia; sem elas, nem mesmo você poderá restaurar os dados.
    * **Nuvem:** A criptografia é considerada *obrigatória* para backups armazenados na nuvem.

#### **5. Tipos de Backup e Métodos Relacionados**

* **Snapshot (Instantâneo):**
    * **Definição:** Um método de backup muito comum em máquinas virtuais (VMs) e infraestruturas de nuvem.
    * **Funcionamento:** Com um clique, cria uma cópia (imagem) da VM em um ponto específico no tempo. É usado antes de grandes atualizações para permitir uma reversão (rollback) rápida.
    * **Natureza:** O primeiro snapshot é completo (ex: 100 GB). Os snapshots seguintes são incrementais, salvando apenas as *alterações* (ex: 40 GB alterados no dia seguinte).

* **Replicação (Replication):**
    * **Definição:** Copia dados de uma fonte para um ou mais locais *simultaneamente* e em *quase tempo real*.
    * **Funcionamento:** Qualquer alteração na fonte é atualizada nos locais replicados em segundos ou minutos.
    * **Uso:** Garante uma cópia exata e atualizada dos dados em outro local. Ideal para *hot sites* (sites de recuperação quentes), permitindo uma transição (failover) imediata em caso de desastre.

* **Journaling (Sistema de Diário):**
    * **Objetivo:** Prevenir a corrupção de dados (ex: em bancos de dados) se houver uma queda de energia *durante* um processo de escrita.
    * **Funcionamento:** A escrita é feita em duas etapas:
        1.  A alteração é primeiro escrita em um arquivo de "diário" (journal).
        2.  Somente *após* o journal ser escrito com sucesso, a alteração é copiada para o banco de dados final.
    * **Recuperação:** Se a energia cair, o sistema verifica o journal ao reiniciar. Se a transação não foi completada no banco de dados, o sistema a refaz usando o journal, garantindo a integridade dos dados.

#### **6. A Etapa Crítica: Testar a Restauração (Restore)**

Fazer o backup é apenas metade do processo. A etapa mais importante é testar a restauração.

* **Problema:** Muitas organizações fazem backups, mas nunca testam se conseguem restaurá-los, descobrindo o problema apenas durante um desastre real.
* **Solução:** Realizar testes de restauração regulares.
* **Validação Completa:** O teste não termina ao apenas restaurar os arquivos. É preciso verificar se as **aplicações** conseguem ler e usar os dados restaurados corretamente.