Resumo do vídeo **Memory Injections - CompTIA Security+ SY0-701 - 2.3**.

***

A **injeção de memória** é uma técnica maliciosa usada para executar um código dentro do espaço de memória de um processo legítimo e confiável. 
O objetivo é fazer com que o código malicioso opere secretamente, escondido sob a identidade de um programa que o sistema operacional e as ferramentas de segurança já confiam.
Essencialmente, em vez de o malware ser executado como um processo separado e suspeito, ele "pega carona" em um processo que já está em execução, como um navegador de internet ou 
um processo do próprio sistema. Isso torna a detecção muito mais difícil, porque, do ponto de vista do sistema, toda a atividade parece ser originada pelo programa legítimo.

### Tipos de Injeção de Memória

## Injeção de DLL (DLL Injection)
É a forma mais comum. O malware força um processo legítimo a carregar uma **DLL (Dynamic-Link Library)** maliciosa em seu espaço de memória. 
Uma vez carregada, o processo executa o código da DLL como se fosse parte de suas operações normais. Para o sistema, parece que o programa confiável está realizando a ação.
