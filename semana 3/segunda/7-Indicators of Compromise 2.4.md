Resumo do vídeo **Indicators of Compromise – CompTIA Security+ SY0-701 – 2.4**

---

EvidÊncias de que um sistema foi invadido são chamadas de **Indicadores de Comprometimento**, ou **IOCs**. Um IOC é um sinal que lhe dá alta confiança de que uma violação de segurança ocorreu.

### **🕵️‍♂️ 1. Atividade Suspeita em Contas de Usuário**

O comportamento das contas de usuário é uma das primeiras coisas a se observar.

* **Contas Bloqueadas:** Sua conta foi bloqueada por excesso de tentativas de senha, mas não foi você quem errou? Isso é um forte sinal de um ataque de força bruta em andamento.
* **Contas Desativadas Misteriosamente:** Se uma conta é desativada administrativamente sem uma solicitação formal, um invasor pode ter obtido acesso de administrador.
* **Logins de Locais "Impossíveis":** Este é um dos IOCs mais claros. Se um usuário faz login do seu escritório no Brasil e, cinco minutos depois, a mesma conta faz login da Austrália, isso é fisicamente impossível e um grande alerta vermelho.
* **Logins Simultâneos:** Embora seja comum estar logado no celular e no desktop, logins simultâneos de locais muito diferentes ou em dispositivos desconhecidos devem ser investigados.

> **Tática do Invasor:** Um invasor pode intencionalmente bloquear sua conta para depois ligar para o *help desk*, se passar por você e pedir para resetar a senha. Isso reforça a necessidade de processos de verificação rigorosos para troca de senhas.

### **🌐 2. Anomalias no Tráfego de Rede**

O fluxo de dados na sua rede pode revelar muita coisa.

* **Picos Inesperados de Tráfego:** Um aumento súbito e maciço no tráfego de rede, especialmente de madrugada ou fora do horário comercial, pode indicar que um invasor está **exfiltrando (roubando) grandes volumes de dados**.
* **Tráfego de Locais Incomuns:** Um aumento no tráfego vindo de países com os quais sua empresa não tem negócios pode ser um sinal de ataque.
* **Alterações no DNS:** Modificações nos servidores DNS podem significar que um invasor está tentando redirecionar seu tráfego para sites maliciosos.

### **💻 3. Comportamento Estranho nos Sistemas e Arquivos**

* **Impossibilidade de Atualizar o Antivírus:** Malware frequentemente desativa as atualizações do antivírus ou bloqueia o acesso a sites de segurança para garantir que ele não seja removido.
* **Arquivos Criptografados:** O sinal mais óbvio de um ataque de **ransomware**. Se você não consegue mais acessar seus dados e encontra pedidos de resgate, a invasão já aconteceu.
* **Alteração de Hashes de Arquivos:** Se os hashes de arquivos críticos do sistema operacional mudaram, significa que eles foram modificados, provavelmente por um malware.
* **Servidores Travando ou Indisponíveis:** Às vezes, a tentativa de um invasor de explorar uma vulnerabilidade pode acabar travando o servidor ou o serviço. A instabilidade sem causa aparente é um IOC.

### **📜 4. Problemas nos Registros (Logs)**

Os logs são o diário de bordo de um sistema, e os invasores sabem disso.

* **Logs Apagados ou com "Buracos":** Para cobrir seus rastros, uma das primeiras ações de um invasor é apagar os logs das atividades que ele realizou. Um "buraco" inexplicável nos registros é um forte indicador de comprometimento.
* **Logs "Fora de Ciclo":** Eventos acontecendo em horários totalmente inesperados. Por exemplo, se os logs mostram que patches de segurança foram instalados às 3 da manhã de um domingo, quando a janela de manutenção é na terça à noite, algo está muito errado.

### **🚨 5. O Indicador Final e Inegável: Vazamento de Dados**

Este é o pior cenário e a prova definitiva de uma invasão.

* **Seus Dados Privados na Internet:** O invasor consegue acesso, rouba suas informações sensíveis e as publica na internet. Às vezes, essa é a primeira vez que a empresa descobre que foi invadida.
* **Chantagem com Ransomware:** A tática moderna dos grupos de ransomware é:
    1.  Invadir a rede.
    2.  **Roubar (exfiltrar) todos os dados sensíveis** para seus próprios servidores.
    3.  Criptografar os dados originais na rede da vítima.
    4.  Exigir um pagamento pelo resgate. Se a vítima não pagar, eles ameaçam **vazar publicamente todos os dados roubados**.