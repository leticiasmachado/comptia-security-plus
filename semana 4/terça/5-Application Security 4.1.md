Resumo do vídeo **Application Security – CompTIA Security+ SY0-701 – 4.1**

---

O processo de criação de aplicações é desafiador, exigindo um equilíbrio entre a velocidade de desenvolvimento e a segurança. Vulnerabilidades como *buffer overflow* ou *injeção de SQL* são frequentemente corrigidas com patches. O ideal é que o time de **QA (Quality Assurance)** encontre essas falhas durante a fase de testes, antes que um atacante as encontre e explore.

#### **1. Validação de Entrada (Input Validation)**

* **Definição:** É a responsabilidade do desenvolvedor de analisar *toda* entrada de dados (formulários, campos de texto, etc.) e garantir que ela corresponda ao formato esperado.
* **Exemplo:** Se um campo pede um CEP, a aplicação deve verificar se a entrada tem o número correto de caracteres e o formato esperado (números, talvez um hífen).
* **Ação:** Se a entrada não seguir o formato, a aplicação deve rejeitá-la e solicitar ao usuário que corrija a informação.
* **Fuzzing:** É um processo de teste automatizado que insere dados **aleatórios** e inesperados nos campos de entrada para ver se a aplicação falha, trava ou se comporta de maneira insegura.

#### **2. Cookies e Segurança**

* **O que são:** Pequenos arquivos de dados armazenados no navegador, usados para rastreamento, personalização de sites e manutenção de sessões de login.
* **O que NÃO são:** Cookies **não são executáveis** e não contêm malware.
* **Risco:** A *informação* dentro do cookie pode ser valiosa. Como eles são fáceis de ler, desenvolvedores **nunca devem armazenar dados sensíveis** (como senhas ou números de cartão de crédito) dentro de um cookie.
* **Secure Cookies:** É um atributo especial que força o cookie a ser transmitido apenas através de conexões criptografadas (**HTTPS**).

#### **3. Análise Estática de Código (SAST)**

* **Definição:** SAST (Static Application Security Testing) é um processo onde o *código-fonte* da aplicação é analisado por uma ferramenta (analisador estático) *antes* de ser compilado ou executado.
* **Objetivo:** Encontrar vulnerabilidades comuns (ex: o uso da função `gets` em C, que é vulnerável a buffer overflow, recomendando a troca por `fgets`).
* **Limitações:**
    * **Não é perfeito:** O SAST pode não encontrar falhas na *implementação* da lógica (ex: uma falha na forma como a criptografia foi usada).
    * **Falsos Positivos:** A ferramenta pode apontar problemas que, na verdade, não são vulnerabilidades. O desenvolvedor precisa revisar toda a saída do analisador.

#### **4. Assinatura de Código (Code Signing)**

* **Problema:** Ao instalar um aplicativo, como saber se ele não foi modificado por um invasor e se realmente veio do desenvolvedor que diz ser?
* **Solução:** Assinatura de Código. É um processo que usa criptografia assimétrica para garantir duas coisas:
    1.  **Integridade:** O código não foi alterado.
    2.  **Autenticidade:** O código realmente se origina do desenvolvedor verificado.
* **Funcionamento:**
    1.  Uma **Autoridade Certificadora (CA)** verifica a identidade do desenvolvedor e emite uma chave assinada.
    2.  O desenvolvedor usa essa chave para "assinar" digitalmente seu aplicativo.
    3.  Durante a instalação, o Sistema Operacional (SO) verifica a assinatura. Se a assinatura for inválida ou rompida, o SO exibirá um aviso de segurança ao usuário.

#### **5. Sandboxing (Isolamento de Aplicação)**

* **Definição:** É uma técnica que executa uma aplicação em um ambiente isolado, limitando seu acesso apenas aos dados e recursos estritamente necessários para seu funcionamento.
* **Tipos de Sandbox:**
    * **Sandbox de Desenvolvimento:** Os desenvolvedores criam e testam o código em um ambiente isolado para não afetar a rede de produção.
    * **Sandbox de Aplicação:** O próprio SO isola os aplicativos uns dos outros.
* **Exemplo:** Em um smartphone, o sistema operacional usa sandboxing. Um navegador pode acessar seus favoritos (que estão no *seu* sandbox), mas ele não pode acessar o rolo da câmera (que está em *outro* sandbox), a menos que o usuário dê permissão explícita. Isso limita o "raio de explosão" de um ataque.

#### **6. Monitoramento e Logs de Aplicação**

* Desenvolvedores podem (e devem) embutir funções de monitoramento na aplicação.
* Isso cria **logs extensivos** que registram como a aplicação está sendo usada.
* A análise desses logs permite identificar comportamentos anômalos, como tentativas de injeção de SQL ou transferências de arquivos incomuns, ajudando a encontrar ataques ou vulnerabilidades desconhecidas.