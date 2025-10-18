Resumo do vídeo **Infrastructure Considerations- CompTIA Security+ SY0-701 – 3.1**

---

### 1. Disponibilidade (Availability)

* **Definição:** É a expectativa de que os recursos de um site ou aplicação (login, transações, etc.) estarão acessíveis e funcionando quando precisarmos deles.
* **A Nuance de Segurança:** Não basta o sistema estar "disponível"; ele deve estar disponível **apenas para as pessoas autorizadas**.
* **Importância:** A TI investe muito em sistemas redundantes e monitoramento complexo para garantir a disponibilidade. O sucesso é frequentemente medido por essa métrica.
* **Métrica Comum:** É descrita como uma porcentagem de tempo. Ex: "Nossa rede esteve disponível 99,999% do tempo" (conhecido como "cinco noves").

### 2. Recuperação e Resiliência (MTTR)

* **O Problema da Interrupção (Outage):** Mesmo com todo o planejamento, falhas (downtime) acontecerão.
* **A Pergunta Chave:** "Quanto tempo vai levar para tudo voltar a funcionar?"
* **A Dificuldade:** É difícil responder imediatamente. Primeiro, é preciso identificar a **causa raiz**:
    * **Hardware:** Exige substituição física.
    * **Software:** Exige a aplicação de um patch ou correção.
    * **Sistemas Redundantes:** Podem precisar ser instalados ou ativados.
* **Métrica Chave (MTTR):** Uma boa medida de resiliência é o **MTTR (Mean Time to Repair)**, ou "Tempo Médio para Reparo". Ele descreve o tempo médio necessário para substituir algo que falhou por um componente funcional.

### 3. Custo (Cost)

* **Fator Decisivo:** O custo é uma das primeiras perguntas ao se implementar qualquer tecnologia.
* **O Custo é Complexo:** Não é um valor único. Ele inclui:
    1.  **Custo de Instalação Inicial:** Pode variar dependendo da plataforma.
    2.  **Custo de Manutenção Contínua:** Pagamentos ao fabricante ou custos internos da equipe de TI.
    3.  **Custo de Substituição:** O custo de reparar ou trocar algo que quebrou.
* **A Visão da Contabilidade:** O cálculo é ainda mais complexo, envolvendo:
    * **Depreciação (Despesa de Capital - CapEx):** O valor do ativo diminuindo ao longo do tempo.
    * **Custos Operacionais (OpEx):** Custos do dia-a-dia para manter o sistema funcionando.
    * **Implicações Fiscais.**

### 4. Responsividade (Responsiveness)

* **Definição:** A rapidez com que um serviço responde a uma solicitação.
* **Fator Humano:** Nós, como humanos, somos muito sensíveis a atrasos (latência).
* **Desafio de Medição:** Pode ser difícil quantificar, pois uma única transação pode envolver múltiplos passos (ex: login $\rightarrow$ consulta ao banco $\rightarrow$ resposta). Algumas funções da aplicação podem ser rápidas, enquanto outras são lentas.

### 5. Elasticidade (Elasticity)

* **O Problema:** O uso de uma aplicação varia (ex: mais acessos no fim do mês ou em um horário de pico).
* **Definição:** A capacidade de **expandir** (aumentar) e **contrair** (diminuir) rapidamente os recursos da aplicação (servidores, etc.) para atender à demanda.
* **Por que não construir sempre no tamanho máximo?** **Custo.** Manter uma infraestrutura gigante o tempo todo é caro.
* **Solução:** Construir um tamanho base e **escalar automaticamente** quando a carga aumenta.
* **Implicação de Segurança:** As ferramentas de segurança devem ser capazes de monitorar a aplicação *inteira*, o que significa que as próprias ferramentas de segurança também precisam ser elásticas e escalar junto com a aplicação.

### 6. Implantação e Orquestração (Orchestration)

* **Aplicações são Complexas:** Uma "aplicação" é, na verdade, um conjunto de muitas partes (servidor web, servidor de banco de dados, servidor de cache, firewall).
* **Desafios de Implantação:** É preciso considerar a infraestrutura técnica, hardware, orçamentos e controle de mudanças.
* **A Solução da Nuvem (Orquestração):** É o processo de **automatizar** a construção de toda essa infraestrutura complexa na nuvem sob demanda. É uma das maiores vantagens da nuvem, permitindo construir ambientes inteiros de forma programática e instantânea.

### 7. Transferência de Risco (Seguro Cibernético)

* **Conceito:** Dada a complexidade e o risco da tecnologia, as organizações podem querer **transferir esse risco** para terceiros.
* **Exemplo Principal:** Contratar um **Seguro Cibernético (Cybersecurity Insurance)**.
* **O que o seguro FAZ:**
    * **Não impede** o ataque (ex: ransomware).
    * Mas **cobre as perdas financeiras** resultantes do ataque.
    * Pode cobrir custos de interrupção, perdas de negócios e até **custos legais** (advogados) se os clientes processarem a empresa.
* **O que o seguro NÃO FAZ:** Ele não substitui a necessidade de boas práticas de segurança.

### 8. Eficiência na Recuperação de Desastres

* **Tempo é Dinheiro:** Quanto mais tempo leva para se recuperar de uma falha, mais dinheiro a organização perde.
* **Planejamento é Essencial:** O processo de recuperação deve ser planejado para ser o mais eficiente possível.
* **Exemplo: Infecção por Malware**
    * **Método 1 (Lento):** Reinstalar o Sistema Operacional (SO) do zero a partir da mídia original. **Tempo: ~1 hora.**
    * **Método 2 (Rápido):** Restaurar o sistema a partir de uma **imagem de backup** (um "snapshot" do sistema limpo). **Tempo: ~10 minutos.**
* Ambos os métodos chegam ao mesmo resultado (sistema limpo), mas o Método 2 é drasticamente mais rápido e, portanto, **mais barato**.

### 9. Gerenciamento de Patches (Patching)

* **A Única Constante é a Mudança:** O software sempre precisará de atualizações.
* **Por que aplicar patches?** Para corrigir bugs, adicionar recursos e, o mais importante, **corrigir falhas de segurança**.
* **O Processo:** É uma parte normal da TI. (Ex: Microsoft lança patches mensais). O processo ideal é:
    1.  Receber o patch.
    2.  **Testar** o patch em um ambiente de homologação (para garantir que ele não quebre nada).
    3.  Implantar o patch nos sistemas de produção o mais rápido possível.
* **O Risco de Não Aplicar Patches:** Deixar de aplicar patches deixa seus sistemas abertos e **suscetíveis a explorações (exploits)**. É um risco de segurança inaceitável.

### 10. O Desafio dos Sistemas Embarcados (Embedded Systems)

* **O Problema:** Alguns sistemas **não são projetados para receber patches**.
* **Exemplos:** Controladores de HVAC (ar-condicionado), relógios de ponto, equipamentos médicos.
* **Por quê?** São sistemas de "propósito único", muitas vezes sem acesso direto à internet, e os fabricantes não criam um processo de atualização.
* **O Risco:** Isso é uma visão "míope". Atacantes encontrarão uma maneira de explorar esses dispositivos. Se uma falha de segurança for descoberta, ela **permanecerá vulnerável**.
* **Mitigação:** Se não é possível aplicar patches, a melhor alternativa é **isolar o dispositivo**. Coloque um **firewall** entre ele e o resto da rede para adicionar uma camada de segurança.

### 11. Energia (Power)

* **O Componente Crítico Esquecido:** Nada funciona sem eletricidade, mas muitas vezes esquecemos de monitorar a infraestrutura de energia.
* **Planejamento:** É essencial trazer um eletricista licenciado para avaliar o uso atual e planejar a expansão futura (as necessidades de um data center são muito diferentes das de um escritório).
* **Backup de Energia:** A energia primária pode falhar. As soluções são:
    * **UPS (Uninterruptible Power Supply / Nobreak):** Baterias para cobrir falhas de curto prazo e permitir um desligamento seguro.
    * **Gerador:** Para cobrir falhas de longo prazo, mantendo a organização funcionando.

### 12. Computação (Compute)

* **Definição:** Em ambientes de nuvem, "computação" é o componente que faz o "trabalho pesado" de **processamento e pensamento** (a CPU).
* **Exemplos:** Um "Compute Engine" na nuvem, ou um processador em um servidor local.
* **Escalabilidade:** Na nuvem, os recursos de computação podem ser escalados (aumentados ou diminuídos) para atender exatamente às necessidades da aplicação.