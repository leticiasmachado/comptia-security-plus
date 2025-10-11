Resumo do vídeo **Zero-day Vulnerabilities – CompTIA Security+ SY0-701 – 2.3**

---

#### **1. A Corrida pelas Vulnerabilidades 🏃‍♂️💨**

Todos os sistemas operacionais e aplicativos que usamos possuem falhas de segurança escondidas. O problema é que ainda não sabemos quais são.

Diariamente, há uma corrida acontecendo:
* **De um lado, os pesquisadores de segurança:** Eles trabalham para encontrar essas falhas e reportá-las de forma responsável aos fabricantes, para que possam ser corrigidas.
* **Do outro lado, os atacantes:** Eles também buscam incessantemente por essas mesmas falhas. O objetivo deles é encontrá-las primeiro para poderem criar ataques e explorá-las em segredo, antes que qualquer correção exista.

#### **2. O que é uma Vulnerabilidade de Dia Zero?**

Uma **vulnerabilidade de Dia Zero (Zero-Day)** é uma falha de segurança que atende a três condições críticas:

1.  É **conhecida pelos atacantes**.
2.  É **desconhecida pelo fabricante** do software.
3.  Consequentemente, **não existe uma correção (patch)** disponível para ela.

#### **3. O Ataque de Dia Zero 💥**

Um **ataque de Dia Zero** é aquele que explora uma vulnerabilidade de Dia Zero. O nome vem da perspectiva do fabricante: ele teve **"zero dias"** para criar uma correção desde que a falha começou a ser explorada ativamente.

> **Analogia:** Imagine que sua casa tem uma falha na fechadura que ninguém conhece, exceto um ladrão. O ladrão pode entrar a qualquer momento. O dia em que a falha se torna pública ou é usada em um crime é o "dia zero". O fabricante da fechadura teve "zero dias" para consertá-la antes que o perigo se tornasse real.

Isso torna a defesa extremamente difícil, pois as ferramentas de segurança tradicionais não têm uma "assinatura" para reconhecer um ataque nunca antes visto. Uma vez que o ataque é descoberto pela comunidade de segurança, inicia-se uma corrida frenética do fabricante para desenvolver e distribuir um *patch* o mais rápido possível.

#### **4. Exemplos Recentes de Ataques de Dia Zero (2023)**

Ataques de Dia Zero são reais e afetam as maiores empresas de tecnologia. Muitos deles já estavam "in the wild" (sendo ativamente explorados por criminosos) quando foram descobertos.

* **Abril de 2023 - Google Chrome:** Uma falha de Dia Zero que permitia corrupção de memória e uma fuga do ambiente de segurança (*sandbox escape*).
* **Maio de 2023 - Microsoft:** Uma falha que permitia que código não autorizado rodasse durante o processo de inicialização segura (UEFI Secure Boot).
* **Maio de 2023 - Apple (iOS e iPadOS):** Três falhas de Dia Zero distintas foram corrigidas, permitindo fuga do *sandbox*, vazamento de informações sensíveis e execução arbitrária de código.

#### **5. Como se Manter Informado? ℹ️**

Para acompanhar as vulnerabilidades conhecidas, incluindo as de Dia Zero que já foram corrigidas, um recurso central é o site **Common Vulnerabilities and Exposures (CVE)**. Ele funciona como um dicionário de todas as falhas de segurança publicamente conhecidas.

**Endereço:** `CVE.mitre.org`
