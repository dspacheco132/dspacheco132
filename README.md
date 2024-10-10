### Diogo Pacheco
[![GitHub followers](https://img.shields.io/github/followers/dspacheco132.svg?style=social&label=Follow&maxAge=2592000)](https://github.com/dspacheco132?tab=followers)

# Arquitetura de Rede AWS (PDL-VPC)

![AWSPROJECT](https://github.com/user-attachments/assets/94cddc6e-107a-4ee0-a96e-58d045d52695)


## Descrição Geral

Este projeto descreve uma arquitetura de rede configurada na Amazon Web Services (AWS), onde está implementado numa **VPC (Virtual Private Cloud)** com a faixa de endereços de **10.0.0.0/20**, dentro da região **us-east-1** da AWS. A configuração inclui ainda uma **sub-rede pública** que possui instancias como um Windows Server (WIN SRV) e vários Windows Client (WIN CLI).

## Componentes da Arquitetura

### 1. **AWS Cloud**
   - Todo este ambiente está a ser executado na **AWS Cloud**, especificamente na região **us-east-1**.

### 2. **PDL-VPC (10.0.0.0/20)**
   - A **VPC** é o ambiente isolado da AWS onde todos os recursos do projeto estão disponiveis.

### 3. **Sub-rede Pública**
   - Todos os acessos remotos dentro desta sub-rede são acessíveis diretamente pela internet através de um **Internet Gateway**.
   - Os principais componentes dentro desta sub-rede são:
     - **WIN SRV**: Windows Server configurado para serviços como o (IIS) e FTP (FileZilla).
     - **WIN CLI**: Máquinas Windows Client conectadas ao **Active Directory** (AD) no domínio **enta.pt**.

### 4. **WIN SRV (Windows Server)**
   - Este servidor é o principal responsável pelos serviços essenciais tais como:
     - **IIS**: Servidor web, com HTTP/HTTPS.
     - **FileZilla**: Servidor FTP que partilha os ficheiros com utilizadores conectados (Maria, Terceira, Corvo), para disponibilizar o diretório do site.
     - Domínios disponíveis no servidor: **oriental.pt**, **central.pt**, **occidental.pt**.
     - IP público do servidor: **3.81.242.104**.

### 5. **WIN CLI 1, 2, 3 (Clientes Windows)**
   - Estas máquinas são clientes conectados ao **Active Directory** do servidor. Cada uma tem um IP público:
     - **WIN CLI 1**: 54.162.230.48
     - **WIN CLI 2**: 107.20.194.40
     - **WIN CLI 3**: 3.209.233.185
   - Estão configuradas para se autenticarem e comunicarem com o **servidor DC | AD** dentro do domínio **enta.pt**.

### 6. **Active Directory (DC | AD)**
   - O **DC (Domain Controller)** realiza a autenticação e o acesso dos clientes **WIN CLI**, permitindo o controlo centralizado dos utilizadores e permissões.

### 7. **Security Group**
   - Controla o tráfego na rede funcionando como um firewall ao nível das instâncias, permitindo ou negando acessos com base em regras configuradas.

### 8. **NACL (Network Access Control List)**
   - Implementado ao nível da sub-rede, controla o tráfego de entrada e saída da sub-rede pública.

### 9. **Internet Gateway**
   - O **Internet Gateway** (IGW) permite que o tráfego da internet aceda aos recursos dentro da **sub-rede pública**. Também permite que as instâncias da sub-rede pública enviem e recebam tráfego da internet.

### 10. **Domínio externo (ciberdsp.hopto.org)**
   - No diagrama tem uma conexão com um domínio externo através do **no-ip** que possibilita a aquisição de 1 hostname, este está direcionado para o IP Publico do Servidor

## Contactos

Sinta-se à vontade para entrar em contato por e-mail:

- E-mail: diogosilvapacheco@enta.pt

Obrigado pela visita! 😉
<!--
**dspacheco132/dspacheco132** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
