Resumo do vídeo **Security Monitoring – CompTIA Security+ SY0-701 – 4.4**

---

### Resumo da Vídeo Aula: Monitoramento de Segurança, SIEM e Resposta a Alertas

#### 1. Por que e O que Monitorar?

Invasores estão constantemente tentando acessar nossos sistemas. Por isso, o monitoramento contínuo é essencial.

* **Objetivo:** Obter visibilidade em tempo real, geralmente através de *dashboards*, para reagir imediatamente a eventos de segurança.
* **O que deve ser monitorado:**
    * **Autenticações e Logins:** Quem está acessando, de onde (um pico de logins de um país onde você não tem funcionários é um alerta) e a que horas.
    * **Serviços e Aplicações:** A atividade, o volume de uso, o status dos backups e as versões de software instaladas (para controle de patches).
    * **Volume de Tráfego:** Um aumento súbito e anormal no tráfego de saída pode indicar uma **exfiltração de dados**.
    * **Infraestrutura de Acesso:** Logs de VPN (para saber quem está conectado: funcionários, fornecedores, etc.) e logs de Firewalls/IPS (para ver picos em tentativas de ataque).

#### 2. O Desafio dos Logs e a Solução: SIEM

Monitorar todos esses sistemas diversos (servidores, firewalls, switches) é um desafio, pois cada um gera logs em formatos diferentes.

* **A Solução: SIEM (Security Information and Event Manager)**
    * É um sistema que **consolida** todos esses arquivos de log de toda a infraestrutura em um **único banco de dados central**.
* **Os Benefícios do SIEM:**
    1.  **Relatórios Centralizados:** Permite gerar relatórios a partir de uma única fonte.
    2.  **Correlação de Dados:** Este é o maior benefício. O SIEM pode cruzar dados de fontes que antes eram isoladas.
    * **Exemplo:** É possível correlacionar um log de *login na VPN* (do firewall) com um log de *acesso a um servidor de arquivos* (do Windows) e um log de *grande volume de dados* (do switch) para identificar um comportamento suspeito completo.

#### 3. Varredura Contínua e Relatórios Acionáveis

Novas vulnerabilidades surgem diariamente, e dispositivos como laptops e celulares estão sempre em movimento.

* **Varredura Contínua:** Por isso, muitas organizações usam sistemas que varrem constantemente a rede para coletar uma "montanha de detalhes" (versão do SO, drivers, apps instalados) e armazená-los em um banco de dados.
* **O Objetivo: Relatórios Acionáveis (Actionable Reports)**
    * Não basta saber o que *está* correto; é preciso saber o que *fazer*.
    * **Exemplo 1 (Conformidade):** O relatório mais importante não é o que mostra os sistemas atualizados, mas sim o que lista os **sistemas que não estão em conformidade** e precisam de patches.
    * **Exemplo 2 (Zero-Day):** Se uma nova vulnerabilidade crítica é anunciada, você pode gerar um relatório imediato: "Quantos sistemas na minha rede estão vulneráveis a esta falha *agora*?"
    * **Exemplo 3 (Relatório "What-If"):** "Este sistema operacional perderá o suporte em 6 meses. Quantos dispositivos precisarão ser atualizados até lá?"

#### 4. A Realidade dos Incidentes e Alertas em Tempo Real

* **Mito (Filmes):** O alarme dispara no instante em que o hacker invade.
* **Realidade (Relatório IBM 2022):** Leva, em média, **9 meses** para uma empresa identificar e conter uma violação.
* **Implicação:** O invasor pode estar na sua rede por meses ou anos. Isso reforça a importância de ter backups de *longo prazo*.
* **A Necessidade de Alertas em Tempo Real:** Você não pode esperar o relatório da manhã seguinte.
    * **Exemplos de Alerta:** Um aumento súbito de erros de autenticação (possível força bruta) ou um pico de transferência de dados (possível exfiltração).
    * **Método:** Os alertas devem ser enviados imediatamente via SMS, e-mail ou para um **SOC (Centro de Operações de Segurança)**.

#### 5. Resposta a Alertas e o Desafio do Ajuste Fino (Tuning)

* **Reação Imediata:** A resposta mais comum a um alerta de segurança crítico é **colocar o sistema em quarentena**.
    * Isso isola o dispositivo da rede, impedindo o invasor de continuar o acesso e de usá-lo para "pular" (movimento lateral) para outros sistemas.
* **O Desafio do Ajuste Fino (Tuning):**
    * **Falso Positivo:** O alarme dispara, mas não é uma ameaça real. Isso gera fadiga na equipe.
    * **Falso Negativo:** Uma ameaça real ocorre, mas *nenhum* alarme é gerado. Este é o pior cenário.
* **Conclusão:** É preciso tempo para "ajustar" (fazer o *tuning*) dos alertas para encontrar o equilíbrio certo, garantindo que sejam precisos e confiáveis para uma tomada de decisão imediata.