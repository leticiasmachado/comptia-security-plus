Resumo do vídeo **Multifactor Authentication – CompTIA Security+ SY0-701 – 4.6**

---

### 1. O que são Fatores de Autenticação?

Fatores de autenticação são os diferentes tipos de parâmetros que usamos para provar nossa identidade ao fazer login em um sistema. Quando você usa um nome de usuário e senha, um código de aplicativo ou sua localização GPS, você está usando esses fatores.

Eles são comumente classificados em quatro categorias principais:
* Algo que você **sabe**
* Algo que você **tem**
* Algo que você **é**
* Onde você **está**

---

### 2. Os Quatro Principais Fatores

#### Fator 1: Algo que Você Sabe (Something You Know)

Este é o fator de autenticação mais popular e inclui qualquer informação que apenas você deveria saber.

* **Senha (Password):** Uma string de caracteres ou uma frase secreta que você memorizou.
* **PIN (Número de Identificação Pessoal):** Um código numérico curto, como o PIN de 4 dígitos usado em um caixa eletrônico (ATM).
* **Padrão (Pattern):** O padrão específico que você desenha na tela de um celular ou tablet para desbloqueá-lo.

#### Fator 2: Algo que Você Tem (Something You Have)

Refere-se a qualquer item físico que você possui e que o identifica.

* **Smart Card (Cartão Inteligente):** Um cartão de identificação que pode ser inserido em um leitor. (Muitas vezes usado em conjunto com um PIN, que é "algo que você sabe").
* **Chave de Segurança USB:** Um dispositivo USB que contém um certificado digital único seu.
* **Token de Hardware:** Um pequeno dispositivo que gera um código numérico pseudoaleatório que muda com frequência, sincronizado com o servidor.
* **Token de Software:** Um aplicativo em seu celular (ex: Google Authenticator) que funciona como um token de hardware, eliminando a necessidade de carregar outro dispositivo.
* **O Próprio Celular:** O simples fato de possuir seu celular pode ser usado, como ao receber um código de uso único por **SMS** (mensagem de texto).

#### Fator 3: Algo que Você É (Something You Are)

Este fator é muito pessoal e está relacionado à **autenticação biométrica** — características únicas do seu corpo.

* **Exemplos:** Impressão digital, impressão de voz, reconhecimento facial ou de íris.
* **Como Funciona:** O sistema **não** armazena uma imagem da sua impressão digital. Em vez disso, ele armazena uma **representação matemática** dela. Quando você se autentica, ele compara a matemática da nova leitura com a matemática armazenada.
* **Desafios:**
    * **Difícil de Alterar:** É muito difícil (ou impossível) "redefinir" sua impressão digital ou voz.
    * **Pode ser Contornado:** Vimos situações em que a biometria foi falsificada ou contornada.
* **Melhor Prática:** Devido a essas fraquezas, a biometria é quase sempre usada em conjunto com outros fatores (como um PIN).

#### Fator 4: Onde Você Está (Somewhere You Are)

Este fator usa sua localização física, geralmente determinada por dispositivos móveis, para permitir ou negar o acesso.

* **Exemplo de Política:** Se você fez login em um local e, 10 minutos depois, uma tentativa de login ocorre em um país diferente, o sistema pode bloquear esse acesso por ser geograficamente impossível.
* **Métodos de Geolocalização:**
    * **Endereço IP:** Pode dar uma ideia geral da sua localização, mas não é um método perfeito (e fica mais difícil com o IPv6).
    * **Coordenadas GPS:** Informações muito mais precisas obtidas do seu dispositivo móvel.
* O sistema pode combinar vários serviços (IP, GPS, etc.) para obter uma geolocalização mais confiável e usá-la como um fator de autenticação.