Resumo do vídeo **Resiliency – CompTIA Security+ SY0-701 – 3.4**

---

#### **1. Alta Disponibilidade (High Availability - HA)**

* **Problema:** Ter apenas componentes de reserva (spare parts) não garante disponibilidade. Se um componente falhar, há um tempo de inatividade (downtime) necessário para desligar o antigo, instalar o novo e configurá-lo.
* **Solução (HA):** Uma configuração onde todos os componentes redundantes já estão instalados, ligados e prontos para assumir.
* **Funcionamento:** Se um sistema primário falha, o sistema secundário assume a carga imediatamente, garantindo que o serviço continue operacional.
* **Desvantagem:** Custo elevado, pois exige a compra de múltiplos sistemas, maior consumo de energia e, muitas vezes, componentes de maior qualidade.

#### **2. Clustering de Servidores (Server Clustering)**

* **Definição:** Vários servidores configurados para trabalhar juntos como se fossem um único e grande servidor. Para o usuário final, eles enxergam apenas uma entidade (o cluster).
* **Benefício (Escalabilidade):** Permite adicionar ou remover servidores (nós) do cluster em tempo real, aumentando ou diminuindo a capacidade conforme a necessidade.
* **Implementação:** Geralmente é uma funcionalidade do próprio sistema operacional. Todos os servidores no cluster costumam rodar sistemas operacionais idênticos.
* **Sincronização:** Para manter os dados consistentes, os servidores do cluster não gravam em seus discos locais. Em vez disso, eles utilizam um **armazenamento compartilhado (shared storage)**, garantindo que todos acessem a mesma informação atualizada.

#### **3. Balanceamento de Carga (Load Balancing)**

* **Definição:** Utiliza um dispositivo central (o balanceador de carga) para distribuir as requisições entre múltiplos servidores individuais.
* **Diferença Chave (vs. Cluster):** No balanceamento de carga, os servidores individuais **não sabem** da existência uns dos outros. O balanceador é o único ponto de gerenciamento.
* **Vantagens:**
    * **Flexibilidade:** Os servidores podem rodar sistemas operacionais diferentes.
    * **Detecção de Falhas:** O balanceador identifica automaticamente se um servidor falhar, remove-o do "pool" e distribui a carga entre os servidores restantes.
    * **Escalabilidade:** Novos servidores podem ser facilmente adicionados ao pool para aumentar a capacidade.

#### **4. Resiliência de Site (Site Resiliency) e Recuperação de Desastres (DR)**

Refere-se a ter locais físicos de recuperação para mover as operações em caso de um desastre que afete o data center principal.

* **Dispersão Geográfica:**
    * **Conceito:** Manter o site de recuperação a uma distância geográfica significativa do site principal.
    * **Propósito:** Proteger contra desastres regionais (ex: furacões, inundações, terremotos) que poderiam afetar ambos os locais se estivessem próximos.
    * **Desafio:** Logística para mover equipamentos e pessoas para o local de recuperação e, eventualmente, trazê-los de volta.

* **Tipos de Sites de Recuperação:**
    * **Hot Site (Site Quente):** Uma réplica exata do data center principal. Contém todo o hardware, aplicações atualizadas e dados constantemente sincronizados. Permite uma recuperação quase imediata.
    * **Cold Site (Site Frio):** Basicamente um "prédio vazio" com energia e refrigeração. É preciso levar todos os equipamentos, dados e pessoas para lá em caso de desastre.
    * **Warm Site (Site Morno):** Um meio-termo. Possui alguns equipamentos e, talvez, alguns dados, mas não é uma réplica completa. Exige a instalação de equipamentos e dados adicionais para operar.

#### **5. Outras Estratégias de Resiliência**

* **Diversidade de Plataforma (Platform Diversity):**
    * **Conceito:** Usar sistemas operacionais (SOs) diferentes (ex: Windows, Linux, macOS) para diferentes funções.
    * **Objetivo:** Vulnerabilidades são, muitas vezes, específicas de um SO. Ao diversificar, evita-se que uma única vulnerabilidade comprometa *todos* os sistemas da organização.

* **Resiliência na Nuvem (Cloud Resiliency):**
    * **Conceito:** Usar múltiplos provedores de nuvem (ex: AWS, Microsoft Azure, Google Cloud).
    * **Objetivo:** Uma falha ou problema de segurança em um provedor não afetará os serviços hospedados em outro, garantindo a continuidade.

#### **6. Planejamento de Continuidade de Operações (COOP - Continuity Of Operations Planning)**

* **Conceito:** O que fazer quando a tecnologia falha completamente (failback)?
* **Foco:** Criar processos **não-técnicos (manuais)** para manter o negócio funcionando.
* **Exemplos:**
    * Preencher formulários de transação manualmente.
    * Emitir recibos em papel.
    * Ligar para a operadora de cartão de crédito para aprovações por telefone.
* **Requisito:** Esses processos devem ser planejados, documentados e testados *antes* que um desastre ocorra.