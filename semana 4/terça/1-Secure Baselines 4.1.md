Resumo do vídeo **Secure Baselines – CompTIA Security+ SY0-701 – 4.1**

---

#### **1. O que é uma Linha de Base de Segurança?**

Uma **Linha de Base de Segurança** (Security Baseline) é um conjunto padronizado de configurações mínimas de segurança que devem ser aplicadas a um sistema ou aplicação.

* **Exemplos:** Configurações de firewall, níveis de patch (atualizações), permissões de arquivos e configurações de segurança do sistema operacional.
* **Implantação:** Cada vez que uma instância da aplicação é implantada, essa linha de base deve ser aplicada junto.
* **Auditoria:** É crucial verificar constantemente se os sistemas continuam em conformidade com a linha de base. Se forem encontradas divergências, um plano deve ser executado para corrigi-las.

#### **2. Como Criar uma Linha de Base?**

Não é preciso começar do zero. Muitos fabricantes já criaram linhas de base fundamentais que podem ser usadas como ponto de partida.

* **Fontes para obter Linhas de Base:**
    * **Desenvolvedor da Aplicação:** Pode fornecer configurações específicas da aplicação e permissões de arquivos.
    * **Fabricante do Sistema Operacional (SO):** Ex: A Microsoft fornece linhas de base de segurança detalhadas para Windows e Windows Server.
    * **Fabricante de Hardware/Appliance:** Fabricantes de dispositivos específicos (como firewalls) também fornecem suas recomendações.

* **Exemplo (Microsoft):**
    * Configurar pode ser complexo. O Windows 10, por exemplo, tem mais de 3.000 configurações de GPO (Group Policy), embora apenas um subconjunto seja focado em segurança.
    * A Microsoft fornece o **Security Compliance Toolkit (SCT)**, uma ferramenta que ajuda a implantar essas linhas de base de segurança.

#### **3. Implantação das Linhas de Base**

Após compilar a lista de configurações, elas precisam ser aplicadas (implantadas) em todos os componentes.

* **Métodos de Implantação:**
    * Consoles centrais (como o SCT da Microsoft).
    * Políticas de Grupo (Group Policy) do Active Directory.
    * Sistemas MDM (Mobile Device Management) para dispositivos móveis.
* **Automação:** Para linhas de base grandes e complexas, a automação é essencial para garantir uma implantação consistente em centenas ou milhares de dispositivos.

#### **4. Manutenção e Atualização**

Linhas de base são, em geral, estáveis (pois são "melhores práticas"), mas precisarão de atualizações em certas situações:

* Quando uma **nova vulnerabilidade** é descoberta.
* Quando a **aplicação é atualizada** e exige novas configurações.
* Quando um **novo SO** é instalado (exigindo uma linha de base totalmente nova).
* Quando há um **conflito** entre as linhas de base de diferentes fabricantes (exigindo uma análise para decidir qual é a melhor para aquela instância).

#### **5. O Ciclo de Vida da Linha de Base**

O processo segue um ciclo contínuo:

1.  **Testar:** As linhas de base devem ser testadas *antes* da implantação.
2.  **Implantar (Deploy):** Aplicar as configurações nos sistemas.
3.  **Auditar:** Verificar regularmente se as configurações permanecem em vigor e não foram alteradas.