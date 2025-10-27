Resumo do vídeo **Firewalls – CompTIA Security+ SY0-701 – 4.5**

---

### 1. O que é um Firewall de Rede?

Um firewall de rede é um dispositivo (appliance) que fica "em linha" na sua rede, tomando decisões sobre permitir ou bloquear o tráfego.

* **Firewall Tradicional:** Toma decisões com base em números de porta (ex: permitir a porta 80 para tráfego web).
* **Firewall de Próxima Geração (NGFW):** É mais moderno e pode tomar decisões com base na aplicação em si (ex: permitir o Facebook, mas bloquear jogos do Facebook).

### 2. Funções Adicionais do Firewall

Firewalls modernos fazem muito mais do que apenas filtrar tráfego:

* **Endpoint de VPN:** Podem atuar como concentradores de VPN, permitindo conexões seguras ponto-a-ponto (entre escritórios) ou de acesso remoto (para funcionários em casa).
* **Roteador (Dispositivo de Camada 3):** Frequentemente atuam como o roteador principal no ponto de entrada/saída da rede (onde a rede interna encontra a internet).
* **Funções de Roteamento:** Por serem roteadores, podem realizar Tradução de Endereços de Rede (NAT), roteamento dinâmico e outras funções de camada 3.

### 3. Foco: Firewall de Próxima Geração (NGFW)

O NGFW é um tipo comum de firewall que analisa o tráfego para reconhecer a aplicação específica que está sendo usada.

* **Nomes Alternativos:** Também pode ser chamado de "Gateway de Camada de Aplicação", "Dispositivo de Inspeção Stateful Multicamada" ou "Dispositivo de Inspeção Profunda de Pacotes (DPI)".
* **Como Funciona:** Ele captura e categoriza os pacotes para identificar a aplicação, o que é um trabalho muito mais complexo do que simplesmente olhar os números das portas.

### 4. Comparativo: NGFW vs. Firewall Tradicional

| Tráfego | Firewall de Próxima Geração (NGFW) | Firewall Tradicional |
| :--- | :--- | :--- |
| **Servidor Web** | Entende "Tráfego Web" | Foca na "Porta TCP 80" ou "TCP 443" |
| **Acesso Remoto** | Entende "SSH" | Foca na "Porta TCP 22" |
| **Área de Trabalho Remota** | Reconhece "Microsoft RDP" | Foca na "Porta TCP 3389" |
| **Resolução de Nomes** | Identifica "Consultas DNS" | Foca na "Porta UDP 53" |
| **Sincronia de Tempo** | Reconhece "NTP" | Foca na "Porta UDP 123" |

### 5. Regras de Firewall (Listas de Controle de Acesso - ACLs)

Uma política de segurança em um firewall é composta por um conjunto de regras, também conhecido como Lista de Controle de Acesso (ACL).

* **Parâmetros da Regra (NGFW):** Uma regra pode incluir nome, IP de origem, IP de destino, serviço (porta), usuário, aplicação, categoria web, URL e outros.
* **Processamento das Regras:** O firewall lê as regras de cima para baixo. A primeira regra que corresponder ao tráfego é aplicada, e o processamento para.
* **Melhor Prática:** Colocar as regras mais específicas no topo da lista e as mais genéricas no final.
* **Negação Implícita (Implicit Deny):** A maioria dos firewalls possui uma regra invisível no final que bloqueia qualquer tráfego que não tenha correspondido a nenhuma regra anterior.

**Exemplo de Processamento de Regra:**
O resumo analisa um conjunto de regras que:
1.  Permite SSH (porta 22)
2.  Permite HTTP (porta 80)
3.  Permite HTTPS (porta 443)
4.  Permite RDP (porta 3389)
5.  Permite DNS (porta 53)
6.  Permite NTP (porta 123)
7.  Nega ICMP (Ping)
8.  **Negação Implícita:** Qualquer outro tráfego (que não corresponda às regras 1-7) é automaticamente bloqueado.

### 6. Posicionamento do Firewall e Sub-redes de Triagem (DMZ)

* **Localização Comum:** O firewall é geralmente colocado no ponto de entrada/saída (ingress/egress) da rede, separando a internet da rede interna.
* **Sub-rede de Triagem (Screened Subnet / DMZ):**
    * É uma rede separada, conectada ao firewall, que fica entre a internet e a rede interna.
    * **Propósito:** Hospedar serviços que precisam ser acessíveis pela internet (como servidores web ou de e-mail).
    * **Segurança:** Isso permite que o tráfego da internet acesse apenas a sub-rede de triagem, impedindo o acesso direto à rede interna, onde ficam os dados confidenciais.

### 7. Sistemas de Prevenção de Intrusão (IPS)

Muitos NGFWs hoje incluem a funcionalidade de um Sistema de Prevenção de Intrusão (IPS).

* **Função:** O IPS monitora o tráfego em tempo real procurando por atividades maliciosas.
* **Detecção por Assinatura:** Utiliza "assinaturas" (padrões de tráfego conhecidos) para reconhecer malwares específicos, como o worm Conficker.
* **Detecção por Anomalia:** Pode também identificar comportamentos suspeitos (anomalias) mesmo sem uma assinatura, como uma tentativa de injeção de banco de dados.
* **Gerenciamento de Regras:** Um IPS pode ter milhares de regras. Elas podem ser agrupadas para facilitar o gerenciamento (ex: criar um grupo "Injeção de Banco de Dados" e bloquear tudo desse grupo).
* **Falsos Positivos:** Um desafio do IPS é que ele pode, ocasionalmente, bloquear tráfego legítimo por engano. Isso exige ajuste e personalização das regras para encontrar o equilíbrio correto entre segurança e funcionalidade.