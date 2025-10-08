Resumo do vídeo "Common Threat Vectors - CompTIA Security+ SY0-701 - 2.2".

O vídeo explica que **vetores de ameaça** são os métodos que os invasores usam para obter acesso a um dispositivo ou rede. Compreender esses caminhos é fundamental para construir defesas eficazes. Messer aborda vários vetores comuns, desde os mais diretos até os mais complexos.

---

### Resumo dos Vetores de Ameaça

* **Vetores Baseados em Mensagens (Message-based):** Utilizam e-mail, SMS (smishing) e mensagens instantâneas para enviar links maliciosos, anexos infectados ou enganar usuários para que revelem informações confidenciais.

* **Vetores Baseados em Imagens (Image-based):** Usam imagens para ocultar código malicioso. Um exemplo específico são os **ataques com imagens SVG**, que, por serem baseadas em texto (XML), podem conter scripts (como JavaScript) que são executados quando a imagem é aberta em um navegador, podendo roubar credenciais ou cookies de sessão.

* **Vetores Baseados em Arquivos (File-based):** Entregam malware através de arquivos. Invasores incorporam macros ou scripts maliciosos em documentos do Word, Excel ou PDFs, que são ativados quando a vítima abre o arquivo.

* **Vetores de Chamada de Voz (Voice Call / Vishing):** Conhecido como "Vishing", este ataque usa engenharia social por telefone. O invasor se passa por uma figura de autoridade (como um técnico de TI ou funcionário de banco) para convencer a vítima a fornecer senhas ou instalar software malicioso.

* **Vetores de Dispositivos Removíveis (Removable Device):** Usam mídias como pen drives USB para introduzir malware em uma rede segura. Um método comum é deixar um dispositivo infectado em um local público para que um funcionário o encontre e o conecte a um computador da empresa.

* **Vetores de Software Vulnerável (Vulnerable Software):** Exploram falhas de segurança em softwares que não foram atualizados. Os invasores usam "exploits" conhecidos para atacar sistemas que não possuem os patches de segurança mais recentes.

* **Vetores de Sistemas Não Suportados (Unsupported System):** Atacam hardware ou software que não recebem mais atualizações de segurança do fabricante (end-of-life). Qualquer vulnerabilidade descoberta nesses sistemas não será corrigida, tornando-os alvos permanentes.

* **Vetores de Redes Inseguras (Unsecure Network):** Exploram redes com segurança fraca, como Wi-Fi abertos sem criptografia, permitindo que invasores interceptem dados (ataque "man-in-the-middle"). O uso de protocolos de texto claro (FTP, Telnet) também se enquadra aqui.

* **Portas de Serviço Abertas (Open Service Ports):** Invasores procuram portas de rede abertas e acessíveis pela internet. Se uma porta associada a um serviço vulnerável é encontrada, eles tentam explorá-la para obter acesso.

* **Credenciais Padrão (Default Credentials):** Muitos dispositivos de rede (roteadores, câmeras IP) são vendidos com senhas padrão fáceis de adivinhar (ex: "admin"/"password"). Se não forem alteradas, os invasores podem usá-las para acessar a rede facilmente.

* **Vetores da Cadeia de Suprimentos (Supply Chain):** Um ataque indireto onde o alvo não é a empresa principal, mas um de seus fornecedores ou parceiros de confiança que tenha acesso à sua rede. Ao comprometer o fornecedor, o invasor ganha um ponto de entrada para o alvo final.