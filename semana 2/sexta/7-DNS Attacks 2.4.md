Resumo do vídeo **DNS Attacks – CompTIA Security+ SY0-701 – 2.4**

---

Nós dependemos do nosso **Serviço de Nomes de Domínio**, ou **DNS**, para traduzir nomes de sites que entendemos (como `bancobrasil.com.br`) em endereços IP que os computadores entendem (como `177.67.202.1`). O DNS funciona como a "lista de contatos" da internet. Mas o que acontece se um invasor conseguir alterar essa lista?

### **DNS Poisoning: Envenenando a "Lista de Contatos" da Internet ☠️**

O **envenenamento de DNS** (ou *DNS Poisoning*) é um tipo de ataque onde um invasor corrompe essa "lista de contatos", fazendo com que um nome de site legítimo aponte para um endereço IP malicioso. O resultado é que o usuário digita o endereço certo, mas é levado para um site falso sem perceber.

Existem diferentes formas de fazer isso:

#### **1. Ataque ao Arquivo `hosts` do Cliente**

* **O que é?** Cada computador possui um arquivo local chamado `hosts`, que funciona como uma mini "lista de contatos" particular que tem prioridade sobre o DNS da internet.
* **Como funciona?** Se um invasor obtiver acesso (geralmente com privilégios de administrador) ao computador de um usuário, ele pode editar esse arquivo e redirecionar sites específicos. Por exemplo, ele pode fazer com que `meubanco.com` aponte para o IP do seu servidor falso.

#### **2. Ataque Man-in-the-Middle (Homem no Meio)**

* **O que é?** O invasor se posiciona "no meio" da comunicação entre o usuário e o servidor DNS.
* **Como funciona?** Quando o usuário pergunta ao DNS "Qual o IP do `site.com`?", o invasor intercepta o pedido e responde primeiro com um IP falso, enganando o navegador do usuário.

#### **3. Ataque Direto ao Servidor DNS**

* **O que é?** É a forma mais poderosa de envenenamento. O invasor consegue acesso administrativo ao próprio servidor DNS.
* **Como funciona?** Uma vez dentro, o invasor altera o registro oficial. No exemplo da aula, ele muda o IP do site `professormesser.com` para o seu próprio IP (`100.100.100.100`). A partir daí, **todos** os usuários que consultarem aquele servidor DNS para acessar o site serão enviados para a página do invasor.

#### **4. Comprometendo o Registro do Domínio**

* **O que é?** O invasor consegue acesso à conta do registrador de domínio (onde o nome do site foi comprado, como GoDaddy ou Registro.br).
* **Como funciona?** Com acesso à conta, o invasor tem controle total e pode alterar para onde o domínio aponta. Os métodos para conseguir esse acesso incluem força bruta, engenharia social para roubar a senha ou usar credenciais vazadas na internet.
* **Exemplo Real:** Em 2016, um banco brasileiro (Banrisul) com mais de 5 milhões de clientes teve **36 de seus domínios sequestrados** por 6 horas. Os invasores ganharam acesso ao registro dos domínios e redirecionaram todo o tráfego do banco (site, app mobile, etc.) para seus próprios servidores, permitindo que coletassem nomes de usuário, senhas e dados financeiros.

---

### **URL Hijacking (Typosquatting): Explorando Erros de Digitação ⌨️**

Este é um ataque diferente, que não envenena o DNS, mas explora um erro humano muito comum: erros de digitação. Também é conhecido como **Typosquatting**.

* **O que é?** Um invasor registra nomes de domínio que são variações ou erros de digitação de sites populares.

* **Exemplos:** Se o site legítimo é `professormesser.com`:
    * **Letra faltando:** `professormeser.com`
    * **Letra trocada:** `professormessor.com`
    * **Letra a mais:** `professormessers.com`
    * **Domínio de topo (TLD) diferente:** `professormesser.org`

#### **O que o Invasor Ganha com Isso?**

Ao levar o usuário para o site falso, o invasor pode:
* **Exibir anúncios** para gerar receita.
* **Vender o domínio** para o dono da marca legítima por um preço alto.
* **Criar uma página de phishing** idêntica à original para roubar seu login e senha.
* **Distribuir malware**, como ransomware ou transformar sua máquina em parte de uma botnet.
* **Redirecionar o tráfego** para um site concorrente.

> **Regra de Ouro:** Sempre **verifique com atenção o endereço na barra do navegador** antes de inserir qualquer informação e **desconfie de links recebidos por e-mail**.