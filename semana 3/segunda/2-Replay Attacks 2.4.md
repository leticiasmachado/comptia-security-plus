Resumo do vídeo **Replay Attacks – CompTIA Security+ SY0-701 – 2.4**

---

Em uma comunicação normal na rede, seu computador (cliente) envia informações para um servidor, e o servidor responde. Um invasor pode tentar capturar essa troca de dados para reutilizá-la posteriormente em um tipo de ataque conhecido como **ataque de Replay**.

### **Ataque de Replay (Replay Attack)**

A ideia de um ataque de Replay é simples: o invasor captura um fluxo de dados legítimo e o **reapresenta** (dá "replay") para o servidor em um momento posterior, na esperança de se passar pelo usuário original.

Pense nisso como gravar alguém dizendo a senha de um cofre por voz e depois tocar essa gravação para o cofre abrir. O sistema é enganado porque recebe um comando que parece autêntico.

* **Como os dados são capturados?** O invasor precisa primeiro obter os dados. Para isso, ele pode usar um grampo físico na rede (*network tap*), realizar um envenenamento de ARP (ataque *Man-in-the-Middle*) ou infectar o computador da vítima com malware.
* **Importante:** Um ataque de Replay em si **não é** um ataque *Man-in-the-Middle*, mas um ataque *Man-in-the-Middle* é uma forma muito comum de obter os dados para o Replay.

#### **Exemplo Prático: Pass the Hash**

Este é um tipo específico de ataque de Replay focado na autenticação.
1.  **O que é um "Hash"?** Quando você digita sua senha, o sistema não a armazena em texto puro. Ele a converte em um código embaralhado e de tamanho fixo chamado **hash**.
2.  **A Captura:** O invasor monitora a rede e captura o momento em que você faz login. Ele obtém seu nome de usuário e o **hash da sua senha** que é enviado para o servidor.
3.  **O Replay:** O invasor então envia esse mesmo par (nome de usuário + hash capturado) para o servidor.
4.  **O Resultado:** O servidor recebe um hash válido, acredita que é o usuário legítimo e concede o acesso ao invasor.

> **🛡️ Como se defender?** A melhor defesa é o uso de **"Salting" (Sal)**. O "sal" é um dado aleatório que é adicionado à sua senha *antes* de gerar o hash. Um bom sistema usa um "sal" diferente para cada sessão de login. Isso garante que o hash seja **diferente a cada vez**, tornando inútil um hash capturado e reapresentado.

---

### **Sequestro de Sessão (Session Hijacking / Sidejacking)**

Enquanto o *Pass the Hash* foca em roubar o momento do login, o sequestro de sessão foca em roubar a **sessão já autenticada**. O invasor não precisa da sua senha; ele só precisa roubar seu "crachá de acesso" digital.

#### **O Papel dos Cookies e IDs de Sessão**

* Quando você faz login em um site, o servidor lhe dá um "crachá" para provar que você está autenticado. Esse crachá é um **cookie** que contém um identificador único chamado **ID de sessão**.
* Seu navegador envia esse cookie com cada nova solicitação para o site, evitando que você precise digitar sua senha a cada clique.

#### **Como o Ataque Acontece?**

1.  **Login:** Você faz login no seu e-mail ou rede social em uma rede não segura (como um Wi-Fi público).
2.  **Captura:** Um invasor na mesma rede usa uma ferramenta (como o Wireshark) para "farejar" o tráfego e captura o cookie com seu ID de sessão.
3.  **O Sequestro:** O invasor agora usa esse ID de sessão roubado para acessar o site. O servidor, ao ver o ID válido, acredita que o invasor é você e concede acesso total à sua conta.



> **🛡️ Como se defender?**
> 1.  **A Regra de Ouro: Criptografia Total (HTTPS)!** A maneira mais eficaz de prevenir o sequestro de sessão é garantir que toda a sua comunicação com o site seja criptografada (procure pelo **cadeado** e **HTTPS** no seu navegador). A criptografia embaralha os dados, incluindo o cookie, tornando-o ilegível para quem estiver espionando.
> 2.  **Use uma VPN:** Em redes públicas, uma VPN (Rede Privada Virtual) cria um "túnel" criptografado entre seu dispositivo e a internet, protegendo todo o seu tráfego.
> 3.  **Extensões de Navegador:** Use extensões que forçam os sites a usarem HTTPS sempre que possível.