Resumo do vídeo **Viruses and Worms – CompTIA Security+ SY0-701 – 2.4**

---

#### **1. O Vírus de Computador 🦠**

Um vírus de computador é um malware que se anexa a um programa ou arquivo e se replica para outros computadores.

* **Característica Principal:** Ele precisa de **intervenção do usuário** para ser ativado. Ou seja, a infecção começa quando uma pessoa clica em um link, abre um anexo ou executa um arquivo infectado.
* **Tipos de Vírus:**
    * **Vírus de Programa:** O tipo clássico, que infecta arquivos executáveis.
    * **Vírus de Setor de Boot:** Infecta a área de inicialização do disco, sendo ativado assim que o computador é ligado.
    * **Vírus de Script:** Injetado em scripts que rodam em navegadores ou outras aplicações.
    * **Vírus de Macro:** Escrito na linguagem de macros de softwares como o Microsoft Office.

##### **O Vírus Sem Arquivo (Fileless Virus): O Inimigo Invisível**

Este é um tipo avançado e furtivo de vírus.

* **Como Funciona:** Ele **não grava arquivos maliciosos no disco rígido**. Em vez disso, opera quase inteiramente na **memória RAM** do sistema. Como a maioria dos antivírus foca em escanear arquivos no disco, esse método o torna muito difícil de detectar.
* **Cadeia de Infecção Típica:**
    1.  O usuário clica em um link malicioso.
    2.  O site explora uma vulnerabilidade (no navegador, Flash, Java, etc.) para executar um código inicial na memória.
    3.  Esse código usa ferramentas legítimas do próprio sistema, como o **PowerShell**, para baixar e executar mais scripts maliciosos, tudo na memória.
    4.  Para sobreviver a uma reinicialização (que limpa a memória RAM), o vírus adiciona uma entrada de inicialização automática no Registro do Windows.

#### **2. O Worm (Verme de Computador) 🐛**

Um worm é um malware autônomo que também se replica, mas com uma diferença crucial.

* **Característica Principal:** Ele **se espalha sozinho, sem qualquer intervenção do usuário**.
* **Como Funciona:** Um worm explora ativamente vulnerabilidades em outros sistemas na rede para se copiar e se propagar. Ele se move na "velocidade da rede", o que pode levar a infecções em massa de forma extremamente rápida.
* **Defesa:** Como ele se move pela rede, firewalls e **Sistemas de Prevenção de Intrusão (IPS)** são essenciais para detectar e bloquear sua propagação.

##### **Estudo de Caso: WannaCry - O Worm que Sequestrava Dados**

O WannaCry é um exemplo perfeito de uma **ameaça híbrida**, combinando as características de um worm com um ransomware.

1.  **Propagação (Worm):** Ele usava a falha **EternalBlue** (uma vulnerabilidade no Windows) para escanear a rede e infectar automaticamente outros computadores vulneráveis.
2.  **Carga Maliciosa (Ransomware):** Uma vez dentro de um novo sistema, ele instalava um ransomware que criptografava todos os arquivos do usuário.
3.  **Ciclo:** A máquina recém-infectada se tornava parte do exército, começando a escanear a rede para encontrar e infectar ainda mais vítimas.

#### **3. Tabela Comparativa: Vírus vs. Worm**

| Característica | Vírus | Worm |
| :--- | :--- | :--- |
| **Início da Infecção** | Requer ação do usuário (clique, execução). | **Automático**, sem ação do usuário. |
| **Propagação** | Anexa-se a arquivos e se move com eles. | Explora vulnerabilidades de rede para se replicar. |
| **Defesa Primária** | Antivírus no computador (endpoint). | Firewall e IPS na rede. |

#### **4. Defesas Comuns**

* **Antivírus:** Essencial para detectar e bloquear a execução inicial de vírus. Mantenha as **assinaturas sempre atualizadas**.
* **Firewalls e IPS:** Cruciais para bloquear a propagação automática de worms pela rede.
* **Manter Sistemas Atualizados:** Corrigir as vulnerabilidades que os worms exploram é a forma mais eficaz de impedi-los.
