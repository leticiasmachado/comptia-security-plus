Resumo do vídeo **Engano e Interrupção (*Deception and Disruption*)**

---

## Estratégias de Engano (Deception)

O principal objetivo dessas tecnologias é criar iscas digitais para desviar o tempo e a atenção dos atacantes.

### 1. Iscas e Armadilhas Digitais

| Conceito | Descrição | Objetivo |
| :--- | :--- | :--- |
| **Honeypot** | Um **sistema** ou recurso **decoy** (isca) único (ex: um servidor virtual) projetado para se parecer vulnerável e atrair atacantes. | Permite que a equipe de segurança estude o **comportamento, as ferramentas e os métodos** de ataque do invasor sem colocar a rede de produção em risco. |
| **Honeynet** | Uma **rede** inteira de *honeypots* e serviços (servidores, roteadores, firewalls falsos) para simular um **ambiente corporativo completo** e mais realista. | Aumenta a complexidade do ambiente de isca para atrair atacantes mais sofisticados. |
| **Honeyfile** | **Arquivos falsos** (como `senhas.txt` ou `segredos_empresa.doc`) colocados em locais estratégicos para atrair um invasor que já está dentro da rede. | Assim que o arquivo é acessado ou aberto, um **alerta** é disparado para a equipe de segurança, indicando uma intrusão. |
| **Honeytoken** | **Dados falsificados** (ex: credenciais de API, números de cartão de crédito inválidos ou endereços de e-mail falsos) inseridos no sistema. | Se o *token* aparecer sendo usado ou distribuído publicamente em outro lugar da internet, a equipe pode rastrear a origem do vazamento ou do ataque. |

### 2. Disrupção

A disrupção é a técnica utilizada para interromper ou bloquear ativamente o progresso de um atacante ou de tráfego malicioso.

* **Sinkhole (Sumidouro):**
    * Mecanismo usado para **redirecionar o tráfego malicioso** (como o tráfego de *botnets* que se comunica com servidores de Comando e Controle - C&C) para um **servidor controlado** pelo defensor.
    * Isso impede que o tráfego chegue ao seu destino pretendido (interrompendo a operação do *malware*) e, ao mesmo tempo, permite que a equipe de segurança **analise** a natureza e a escala do ataque.