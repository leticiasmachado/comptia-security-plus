Resumo do vídeo **Security Tools – CompTIA Security+ SY0-701 – 4.4**

---

#### 1. O Problema da Padronização: SCAP

* **O Desafio:** Você tem muitas ferramentas de segurança (firewall, IPS, scanner de vulnerabilidade). Todas podem identificar a *mesma* falha, mas usam nomes, termos e descrições diferentes.
* **A Solução: SCAP (Security Content Automation Protocol)**
    * É um protocolo padrão mantido pelo NIST (`scap.nist.gov`).
    * **Função:** Consolida as vulnerabilidades em uma **linguagem única** que todos os dispositivos entendem.
    * **Benefício (Automação):** Agora as ferramentas podem trabalhar juntas. Um scanner pode encontrar uma falha, informar o sistema de gerenciamento, e o sistema pode aplicar um patch automaticamente, tudo sem intervenção humana.

#### 2. Configuração Segura: CIS Benchmarks

* **Definição:** O CIS (Center for Internet Security - `cissecurity.org`) compila listas de *melhores práticas* (benchmarks) para "endurecer" (harden) sistemas operacionais, aplicativos e conexões em nuvem.
* **Objetivo:** Configurar um sistema para ser o mais seguro possível desde o início.
* **Exemplo (Dispositivo Móvel):** Um benchmark pode forçar backups criptografados, desabilitar capturas de tela e impedir chamadas de voz quando o sistema estiver bloqueado.

#### 3. Verificação de Conformidade: Agente vs. Sem Agente (Agentless)

Como verificamos se os dispositivos seguem esses benchmarks?

* **Com Agente (Agent-based):**
    * Um software é instalado permanentemente no dispositivo.
    * **Vantagem:** Está sempre em execução (24/7), monitorando a conformidade.
    * **Desvantagem:** Requer manutenção e atualização contínua do próprio agente.
* **Sem Agente (Agentless):**
    * Nenhum software é instalado permanentemente.
    * **Vantagem:** Roda sob demanda (ex: ao logar na VPN), executa na memória, verifica a conformidade e depois se remove. Não requer manutenção.
    * **Desvantagem:** Não está em execução 24/7.

#### 4. SIEM (Security Information and Event Manager) - Revisão

* **Função Principal:** Consolida logs de diversas fontes em um banco de dados central.
* **Poder:** Além dos relatórios, seu maior valor está na **correlação de dados** (ex: cruzar um log de VPN com um log de servidor de aplicação e um log de firewall).
* **Uso Forense:** Como armazena dados por um longo período, é usado para investigações forenses, permitindo "voltar no tempo" para entender como um incidente de segurança ocorreu.

#### 5. Antivírus e Anti-Malware

* **Função:** Identifica software malicioso (Trojans, worms, ransomware, spyware, etc.).
* **Nota:** Embora "malware" seja um termo amplo, hoje em dia os termos "antivírus" e "anti-malware" são usados de forma intercambiável e se referem essencialmente ao mesmo tipo de software de proteção.

#### 6. DLP (Data Loss Prevention - Prevenção contra Perda de Dados)

* **Função:** Monitora e bloqueia ativamente a transferência de dados sensíveis.
* **O que ele procura:** Números de CPF, informações médicas, dados de cartão de crédito, etc.
* **Onde atua:** Pode ser um software no *endpoint* (computador do usuário), um *appliance* na rede ou um sistema baseado em *nuvem* para monitorar o tráfego que já está na nuvem.

#### 7. SNMP (Simple Network Management Protocol)

* **Função:** Coleta métricas de baixo nível de dispositivos de rede (ex: utilização de CPU, bytes transferidos em uma interface).
* **Componentes:**
    * **MIB (Management Information Base):** O banco de dados no dispositivo que armazena as métricas.
    * **OID (Object Identifier):** Um "endereço" numérico para cada métrica específica.
* **Métodos de Coleta:**
    * **Polling (Porta UDP 161):** A estação de gerenciamento "pergunta" (pol) ao dispositivo pelos dados em intervalos regulares (ex: a cada 5 minutos).
    * **Traps (Porta UDP 162):** O dispositivo *proativamente* envia um alerta (trap) para a estação de gerenciamento quando um limite é atingido (ex: o número de erros excede 5).

#### 8. NetFlow

* **Função:** Focado em monitorar *fluxos de tráfego* e estatísticas de uso de *aplicação* (quem está falando com quem e quanto).
* **Componentes:**
    * **Probe (Sonda):** Coleta as métricas. Pode ser um software embutido no switch/roteador ou um dispositivo físico separado (conectado a uma porta SPAN ou TAP).
    * **Collector (Coletor):** Recebe os dados das sondas e gera os relatórios.
* **Relatórios Típicos:** "Top 10 Conversas", "Top 10 Endpoints por Tráfego", etc.

#### 9. Scanner de Vulnerabilidade - Revisão

* **Função:** Projetado para ser minimamente invasivo. Ele verifica *potenciais* vulnerabilidades, mas **não** executa *exploits*.
* **Recursos:** Também realiza *port scans* para ver quais serviços estão ativos.
* **Perspectiva:** É útil executar varreduras de *dentro* da rede e também de *fora* da rede (para ter a perspectiva de um invasor).
* **Aviso:** Scanners coletam muitas informações, e nem tudo é 100% preciso. Os resultados sempre precisam ser verificados para identificar falsos positivos.