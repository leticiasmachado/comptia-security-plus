Resumo do vídeo **Mitigation Techniques – CompTIA Security+ SY0-701 – 2.5**

---

**Mitigação** é o processo de reduzir o impacto de um evento de segurança, seja ele potencial ou já em andamento. Em vez de apenas reagir, a mitigação foca em estratégias para minimizar os danos. Vamos explorar as principais técnicas.

### **1. Gerenciamento de Patches: Fechando as Portas Antes do Ataque 🚪**

A melhor forma de parar um ataque é antes que ele aconteça. Manter os sistemas atualizados é fundamental.

* **O que é?** Aplicar **patches** (correções) de segurança fornecidos por fabricantes (como Microsoft, Apple) e desenvolvedores de software para consertar vulnerabilidades conhecidas.
* **Como funciona?**
    * Em casa, seu sistema operacional geralmente faz isso **automaticamente**.
    * Em grandes empresas, o time de TI primeiro **testa os patches** para garantir que não causem problemas, e só depois os distribui para todos os computadores.
* **Patches de Emergência:** Para falhas críticas que estão sendo ativamente exploradas, os fabricantes liberam patches de emergência fora do cronograma normal.

### **2. Criptografia: Protegendo os Dados em Caso de Roubo 🔒**

Se um invasor conseguir roubar um dispositivo, a criptografia garante que os dados contidos nele sejam inúteis.

* **Níveis de Proteção:**
    * **Criptografia de Nível de Arquivo:** Você pode criptografar arquivos ou pastas específicas. No Windows, isso é feito com o **EFS (Encrypting File System)**.
    * **Criptografia de Disco Inteiro (FDE):** Criptografa **tudo** no disco rígido ou SSD, incluindo o sistema operacional e todos os seus arquivos. É essencial para notebooks. Exemplos: **BitLocker** (Windows) e **FileVault** (macOS).
    * **Criptografia na Aplicação:** O próprio software criptografa seus dados, adicionando uma camada extra de segurança.

### **3. Monitoramento e Logs (SIEM): Olhos e Ouvidos da Rede 📈**

Para identificar um evento de segurança, você precisa estar observando e registrando o que acontece.

* **O que é?** Coletar **logs** (registros de eventos) de todos os seus dispositivos de rede (firewalls, roteadores, servidores).
* **Centralização com SIEM:** Como os logs vêm de muitos lugares, usamos uma ferramenta chamada **SIEM (Security Information and Event Management)** para consolidar tudo em um único local. Isso facilita a análise, a geração de relatórios e a detecção de anomalias.

### **4. Princípio do Menor Privilégio: Dê Apenas a Chave Necessária 🔑**

* **O que é?** Conceder a cada usuário **apenas as permissões mínimas e estritamente necessárias** para que ele realize seu trabalho, e nada mais.
* **Por que é importante?** Se a conta de um usuário comum for comprometida, o dano que o invasor pode causar é limitado ao que aquele usuário podia fazer. Isso impede que um ataque pequeno se transforme em um desastre em toda a empresa.
* **Melhor Prática:** Ninguém deve usar uma conta de administrador para tarefas do dia a dia. As permissões devem ser elevadas temporariamente apenas quando necessário.

### **5. Avaliação de Postura (Posture Assessment): O "Segurança" na Porta da Rede 👮**

* **O que é?** Antes de permitir que um dispositivo se conecte à rede corporativa, o sistema verifica sua "postura" de segurança para ver se ele cumpre os requisitos mínimos.
* **O que é verificado?**
    * O antivírus está instalado e atualizado?
    * O sistema operacional tem os últimos patches de segurança?
    * O firewall local está ativo?
* **Quarentena:** Se o dispositivo falhar na verificação, ele é colocado em uma rede de **quarentena**, isolada do resto da empresa. Lá, o usuário só pode acessar os recursos necessários para corrigir os problemas. Após as correções, ele pode tentar se conectar novamente.

### **6. Descomissionamento Seguro: O Fim da Linha 🗑️**

Quando um equipamento chega ao fim de sua vida útil, não basta simplesmente desligá-lo e guardá-lo.

* **O Risco:** Discos rígidos, SSDs e pen drives de equipamentos antigos podem conter informações sensíveis.
* **Procedimento Correto:**
    * **Reutilização Interna:** O disco deve ser formatado de forma segura antes de ser movido para outro computador.
    * **Descarte:** Se o disco não for mais usado e contiver dados sensíveis, a forma mais segura de garantir que ninguém jamais acesse esses dados é a **destruição física** (trituração, perfuração, etc.).