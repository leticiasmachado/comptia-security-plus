Resumo da vídeo aula "Authentication, Authorization, and Accounting - CompTIA Security+ SY0-701 - 1.2". Ela trata de um dos pilares da segurança da informação em redes e sistemas: o framework **AAA**, que significa **Authentication, Authorization, and Accounting** (Autenticação, Autorização e Contabilidade).

---

## Resumo: O Framework AAA

O vídeo descreve o processo de controle de acesso de um usuário (ou sistema) a um recurso, dividindo-o em três etapas distintas e sequenciais:

### 1. Authentication (Autenticação)

É a etapa de **provar a identidade** alegada. O sistema verifica se o usuário é realmente quem diz ser.

* **Identificação (Identification):** É a primeira parte, onde o usuário **alega** uma identidade (geralmente fornecendo um **nome de usuário**).
* **Autenticação (Authentication):** É a prova dessa alegação. O usuário precisa fornecer fatores de autenticação que comprovem a identidade.
    * **Métodos Comuns:** Senha, token (software ou hardware), dados biométricos (impressão digital), ou um certificado digital.
* **Autenticação de Sistemas:** O framework AAA também se aplica a sistemas, que usam **certificados digitais** assinados por uma Autoridade Certificadora (CA) para provar sua identidade na rede.

### 2. Authorization (Autorização)

Depois que a identidade é comprovada, esta etapa determina **o que o usuário tem permissão para fazer**.

* O sistema verifica os direitos e permissões de acesso do usuário (ou sistema) aos recursos da rede, como arquivos, pastas, servidores ou funcionalidades de aplicativos.
* **Modelos de Autorização:** Para simplificar a gestão em larga escala, são usados **Modelos de Autorização (Authorization Models)**, onde os usuários são associados a **grupos** ou **funções (roles)**. Em vez de atribuir permissões individualmente a cada usuário, as permissões são atribuídas à função, simplificando a administração.

### 3. Accounting (Contabilidade)

Esta etapa é o **registro e rastreamento** das atividades do usuário enquanto ele está acessando o sistema.

* É o log das ações tomadas (por exemplo, "o usuário X acessou o arquivo Y", "o usuário Z tentou entrar no servidor A e falhou").
* O *Accounting* cria uma **trilha de auditoria** que pode ser usada para fins de **Não Repúdio (Non-repudiation)**, auditoria de segurança, e análise forense em caso de incidentes.

Em resumo, o AAA é o ciclo completo que garante que: **Você é quem diz ser (Autenticação), tem permissão para fazer o que está tentando (Autorização), e todas as suas ações estão sendo registradas (Contabilidade).**

#### Certificados digitais
Pense em um **Certificado Digital** como o **passaporte** de um dispositivo. Ele contém a identidade do dispositivo e uma chave pública, sendo **assinado digitalmente** por uma CA. A **Entidade Certificadora (CA)** é a parte mais importante: ela é uma **terceira parte confiável** que valida a identidade do dispositivo antes de emitir o certificado, garantindo que ele seja legítimo.
