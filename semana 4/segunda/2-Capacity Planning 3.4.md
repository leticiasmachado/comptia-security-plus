Resumo do vídeo **Capacity Planning – CompTIA Security+ SY0-701 – 3.4**

---

O gerenciamento de capacidade é um desafio constante em TI, focado em prever e suprir a demanda por um serviço. O objetivo é encontrar o equilíbrio perfeito entre oferta (recursos) e demanda (uso).

* **Oferta Insuficiente (Oferta < Demanda):** Causa lentidão nas aplicações e potenciais interrupções (outages).
* **Oferta Excessiva (Oferta > Demanda):** Resulta em desperdício de dinheiro, pois recursos foram comprados desnecessariamente.

Para atingir o equilíbrio ideal, o planejamento deve considerar três componentes principais: pessoas, tecnologia e infraestrutura.

#### **1. O Fator Humano na Escalabilidade**

Embora o foco seja tecnológico, o componente humano é crucial e difícil de escalar.

* **Exemplo:** Um call center precisa de aplicações, mas também de pessoas para atender os telefones.
* **Desafios da Escalabilidade Humana:**
    * **Aumentar (Ramp Up):** É um processo lento e caro. Exige contratar e treinar novos funcionários.
    * **Reduzir (Ramp Down):** Funcionários representam uma grande despesa. Reduzir a equipe pode exigir remanejamento ou demissões (downsizing).

#### **2. Escalabilidade da Tecnologia**

A tecnologia escolhida deve ser capaz de crescer e encolher (escalar) facilmente para atender à demanda. Isso deve ser planejado desde a fase inicial do projeto.

* **Exemplo 1: Servidores Web**
    * **Solução:** Implementar balanceadores de carga (load balancers) e múltiplos servidores.
    * **Funcionamento:** Permite adicionar mais servidores "por trás dos panos" durante picos de demanda e removê-los quando a demanda diminui, de forma invisível para o usuário.

* **Exemplo 2: Bancos de Dados**
    * **Soluções:** Habilitar múltiplos servidores SQL ou dividir (particionar) o banco de dados em partes menores, distribuindo-as por vários servidores.

#### **3. O Papel da Nuvem na Implantação e Escalabilidade**

Os serviços em nuvem mudaram fundamentalmente a forma como a capacidade é gerenciada.

* **Implantação (Deployment): Data Center Físico vs. Nuvem**
    * **Data Center Físico:** Um processo lento e trabalhoso. Envolve comprar hardware, esperar a entrega, desempacotar, configurar, instalar no rack, testar e, finalmente, implantar.
    * **Nuvem (Cloud):** Um processo muito mais fácil. Não há aquisição de hardware. Novas instâncias de aplicação podem ser criadas com apenas alguns cliques em um console web.

* **Benefícios da Nuvem:**
    * **Escalabilidade Rápida:** Permite aumentar (ramp up) rapidamente os recursos durante picos de demanda.
    * **Dimensionamento Correto (Rightsizing):** Permite reduzir (ramp down) facilmente a infraestrutura quando a demanda cai, garantindo que você pague apenas pelo que está usando.