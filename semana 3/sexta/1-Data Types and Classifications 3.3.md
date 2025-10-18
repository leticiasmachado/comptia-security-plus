Resumo do vídeo **Data Types and Classifications – CompTIA Security+ SY0-701 – 3.3**

---

### 1. Introdução ao Gerenciamento de Dados

O ativo mais importante de uma organização são seus **dados**. No entanto, nem todos os dados são iguais. A forma como gerenciamos e protegemos os dados muda drasticamente dependendo de *quem* os possui e *o que* estamos fazendo com eles.

---

### 2. Tipos de Dados por Natureza e Regulação

1.  **Dados Regulamentados (Regulated Data):**
    * São dados cujas regras de proteção são definidas por um **terceiro** (governo ou órgão industrial).
    * **Exemplo:** Informações de cartão de crédito devem seguir as regras do **PCI-DSS (Payment Card Industry Data Security Standard)**. Leis governamentais (como LGPD ou GDPR) também ditam como os dados podem ser armazenados e por quanto tempo.

2.  **Segredos Comerciais (Trade Secrets):**
    * Processos, fórmulas ou informações conhecidas **apenas pela organização**. São o que dão à empresa uma vantagem competitiva.
    * A segurança aqui é crucial, pois concorrentes adorariam ter acesso a eles.

3.  **Propriedade Intelectual (Intellectual Property - IP):**
    * Um tipo de dado que muitas vezes *é* visível ao público, mas é protegido de forma diferente.
    * A proteção é feita através de meios **legais**, como **direitos autorais (copyrights)** e **marcas registradas (trademark law)**.

4.  **Informações Legais (Legal Information):**
    * Apresentam um desafio único: balancear o público e o privado.
    * **Informação Pública:** Em muitas regiões, registros de tribunal, nomes de juízes e advogados são públicos.
    * **Informação Privada:** Detalhes dentro desses processos (como PII ou outros dados sensíveis) devem ser protegidos, muitas vezes sendo armazenados em sistemas separados.

5.  **Detalhes Financeiros (Financial Details):**
    * Um tipo claro de informação sensível.
    * Isso inclui tanto os dados financeiros **internos** de uma empresa (que devem ser privados) quanto seus dados financeiros **pessoais** (informações de conta bancária, pagamentos, etc.).

---

### 3. Legibilidade dos Dados

Os dados podem existir em formatos diferentes:

* **Legível por Humanos:** Fácil de entender à primeira vista (documentos de texto, planilhas).
* **Não Legível por Humanos:** Dados codificados que requerem um computador para interpretar (código de barras, arquivos binários, imagens criptografadas).
* **Formato Híbrido:** Uma combinação dos dois. O exemplo clássico é um **código de barras** (não legível por humanos) com os **números impressos abaixo dele** (legível por humanos).

---

### 4. Por que Classificar os Dados?

Diferentes tipos de dados possuem diferentes **níveis de sensibilidade**.
* **Exemplo:** A placa de um carro (que pode ser consultada publicamente em alguns lugares) tem uma sensibilidade muito menor do que seu **histórico médico** (que nunca deve ser acessível a outros).

**Classificar** os dados nos permite aplicar os controles de segurança corretos:
1.  **Permissões Específicas:** Apenas indivíduos autorizados podem acessar.
2.  **Processos Diferenciados:** Pode exigir etapas extras de verificação para visualizar dados muito sensíveis.
3.  **Áreas Restritas:** Criar segmentos de rede isolados onde apenas pessoas específicas podem acessar aqueles dados.

---

### 5. Definições-Chave de Dados (PII e PHI)

Existem categorias de dados sensíveis que são universalmente reconhecidas:

1.  **Dados Proprietários (Proprietary Data):**
    * São dados que **pertencem** à organização e são usados apenas por ela.
    * São únicos daquela empresa (como segredos comerciais) e não devem ser encontrados fora dela.

2.  **PII (Personally Identifiable Information):**
    * **Informações de Identificação Pessoal**.
    * São quaisquer dados que possam ser usados para **identificar um indivíduo específico**.
    * **Exemplos:** Nome completo, data de nascimento, nome de solteira da mãe, dados biométricos, endereço residencial.

3.  **PHI (Protected Health Information):**
    * **Informações de Saúde Protegidas**.
    * São quaisquer detalhes de saúde **específicos de um indivíduo**.
    * **Exemplos:** Status da sua saúde, registros médicos, pagamentos feitos por cuidados de saúde.

---

### 6. Rótulos de Classificação de Dados

Com base na sensibilidade, podemos criar diferentes classificações (rótulos) para os dados, que por sua vez definem os níveis de acesso:

* **Sensível (Sensitive):** Uma categoria ampla que geralmente inclui Propriedade Intelectual, PII e PHI.
* **Confidencial (Confidential):** Dados que são ainda mais sensíveis e exigem autorizações adicionais para visualização.
* **Público / Não Classificado (Public / Unclassified):** (Comum em governos) Informações que qualquer pessoa pode ver.
* **Privado / Classificado / Restrito (Private / Classified / Restricted):** Exige permissões mais altas ou até mesmo a assinatura de um **NDA (Acordo de Confidencialidade)** para ter acesso.
* **Crítico (Critical):** Uma classificação especial que foca na **Disponibilidade**. São dados que devem estar **sempre acessíveis** (ex: sistemas de controle de uma usina). Os processos e procedimentos devem garantir o uptime desses dados.