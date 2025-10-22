Resumo do vídeo **Power Resiliency – CompTIA Security+ SY0-701 – 3.4**

---

A energia elétrica é o recurso fundamental que conecta todas as tecnologias em um data center. Como a maioria das organizações não gera sua própria energia e depende de provedores locais, elas estão sujeitas a falhas na rede elétrica (apagões). Por isso, é essencial projetar sistemas de energia de backup.

#### **1. Solução de Curto Prazo: UPS (Uninterruptible Power Supply)**

O UPS, ou Fonte de Alimentação Ininterrupta, fornece energia temporária através de baterias internas, protegendo os sistemas contra:

* **Blackouts:** Apagões completos.
* **Brownouts:** Quedas na voltagem (subtensão).
* **Surges:** Picos de voltagem (sobretensão).

**Tipos de UPS:**

* **Offline / Standby (Standby UPS):**
    * O tipo mais básico e de menor custo.
    * Funciona com a energia principal e possui uma chave interna.
    * Quando a energia principal falha, a chave muda para a bateria.

* **Linha Interativa (Line-interactive UPS):**
    * Ideal para áreas com muitos *brownouts*.
    * Consegue "aumentar" a voltagem lentamente se houver uma queda na rede elétrica, sem precisar usar a bateria.

* **Online / Dupla Conversão (Online UPS):**
    * O mais robusto. Os sistemas estão *sempre* rodando a partir da energia da bateria (que é constantemente recarregada).
    * Não há tempo de "troca" (chaveamento), pois a energia já está vindo da bateria.

**Recursos Adicionais do UPS:**

* **Capacidade da Bateria:** Define por quanto tempo o UPS pode manter os sistemas ligados.
* **Desligamento Automático (Graceful Shutdown):** Quando a bateria está acabando, o UPS pode enviar um sinal aos servidores para que eles desliguem de forma organizada, antes que a energia acabe abruptamente.
* **Outras Proteções:** Alguns modelos incluem supressores para cabos de rede (Ethernet) ou telefone.

#### **2. Solução de Longo Prazo: Gerador (Generator)**

* **Função:** Fornece energia de backup por longos períodos (horas ou dias).
* **Requisito:** Continua a fornecer energia desde que haja **combustível** (ex: diesel, gás natural).
* **Tipos:**
    * **Total:** Grande o suficiente para alimentar um prédio inteiro.
    * **Parcial:** Alimenta apenas um conjunto específico de tomadas (geralmente marcadas em vermelho) para sistemas críticos.

#### **3. A Estratégia Combinada: UPS + Gerador (A Melhor Prática)**

Organizações críticas utilizam **ambos** os sistemas em conjunto, pois eles resolvem problemas diferentes:

1.  A energia da rua **falha**.
2.  O **UPS** assume a carga **imediatamente**, mantendo os servidores ligados (sua bateria dura minutos).
3.  O **Gerador** detecta a falha e inicia seu processo de "ramp-up" (inicialização), o que pode levar cerca de um minuto.
4.  Durante esse minuto, o UPS "cobre o buraco" (gap) de energia.
5.  Quando o Gerador está estável, ele assume a carga do prédio e o UPS para de usar sua bateria.

O **UPS** garante a transição imediata, e o **Gerador** garante a alimentação a longo prazo.