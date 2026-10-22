# Segurança de Roteador Wireless

## Visão geral

Neste laboratório da **Cisco Networking Academy (NetAcad)**, utilizei o **Cisco Packet Tracer** para praticar a configuração de segurança de um roteador doméstico.

A atividade envolveu a proteção do acesso administrativo, a criação de uma rede principal (`HomeNet`) e outra para convidados (`GuestNet`), além da conexão de computadores e dispositivos inteligentes.

O objetivo foi entender como **proteger uma rede wireless, controlar o acesso dos visitantes e verificar a comunicação entre os dispositivos**.

<img width="619" height="410" alt="image" src="https://github.com/user-attachments/assets/b32c5b7d-0467-49d0-891d-cc051cd25f39" />


---

## Topologia da rede

![Cenário doméstico do laboratório](ambiente-domestico.png)

O ambiente simula uma residência com computadores e dispositivos inteligentes conectados a um roteador.

A rede principal é utilizada pelos moradores, enquanto a rede de convidados permite oferecer acesso à Internet com restrições de comunicação com a rede interna.

---

## O que pratiquei

* Alteração da senha padrão de administração do roteador.
* Desativação do gerenciamento remoto.
* Configuração de redes wireless nas faixas de 2,4 GHz e 5 GHz.
* Proteção das conexões com WPA2 Personal e AES.
* Criação de uma rede separada para convidados.
* Conexão de computadores e dispositivos IoT.
* Configuração automática de endereços IP por DHCP.
* Verificação de conectividade e isolamento de rede.

---

## Como o laboratório foi desenvolvido

1. **Proteção do roteador:** acesso à página administrativa, alteração da senha padrão e desativação do gerenciamento remoto.
2. **Rede principal:** configuração da `HomeNet` com autenticação WPA2 Personal e criptografia AES.
3. **Rede de convidados:** criação da `GuestNet` com senha própria e restrição de acesso à rede local.
4. **Conexão dos dispositivos:** associação dos notebooks e equipamentos inteligentes às redes correspondentes.
5. **Endereçamento:** utilização de DHCP para atribuir endereços IPv4 automaticamente.
6. **Verificações:** testes de conectividade e comunicação entre as redes antes e depois da configuração de isolamento.

---

## Configurações dos dispositivos

### 1. Roteador e redes wireless

O roteador foi utilizado para administrar as conexões e aplicar as configurações de segurança.

| Parâmetro                          | Configuração                 |
| ---------------------------------- | ---------------------------- |
| **Endereço do roteador**           | `192.168.0.1`                |
| **Rede local**                     | `192.168.0.0/24`             |
| **Máscara de rede**                | `255.255.255.0`              |
| **Gateway**                        | `192.168.0.1`                |
| **Senha administrativa**           | Substituição da senha padrão |
| **Gerenciamento remoto**           | Desativado                   |
| **Endereçamento dos dispositivos** | DHCP                         |

### 2. Configurações de segurança das redes

| Parâmetro               | Rede principal                    | Rede de convidados            |
| ----------------------- | --------------------------------- | ----------------------------- |
| **SSID**                | `HomeNet`                         | `GuestNet`                    |
| **Faixas wireless**     | 2,4 GHz, 5 GHz-1 e 5 GHz-2        | 2,4 GHz, 5 GHz-1 e 5 GHz-2    |
| **Segurança**           | WPA2 Personal                     | WPA2 Personal                 |
| **Criptografia**        | AES                               | AES                           |
| **Senha de acesso**     | Própria da rede principal         | Própria da rede de convidados |
| **Acesso à rede local** | Permitido conforme a configuração | Bloqueado para convidados     |
| **Divulgação do SSID**  | Habilitada                        | —                             |

### 3. Computadores e dispositivos inteligentes

Os equipamentos foram distribuídos entre a rede principal, a rede de convidados e a conexão por cabo.

| Dispositivo        | Conexão      | Configuração                     |
| ------------------ | ------------ | -------------------------------- |
| **Home Office PC** | Cabo de rede | DHCP e administração do roteador |
| **Home Laptop 1**  | HomeNet      | WPA2 Personal                    |
| **Home Laptop 2**  | GuestNet     | WPA2 Personal                    |
| **Home_Webcam**    | HomeNet      | WPA2-PSK, AES e DHCP             |
| **Home_Siren**     | HomeNet      | Wireless e DHCP                  |
| **Home Door**      | HomeNet      | Wireless e DHCP                  |

**Observação:** os endereços IPv4 individuais dos dispositivos não foram informados no material. As senhas utilizadas pertencem ao ambiente simulado do laboratório.

---

## Testes e verificações

A atividade incluiu procedimentos para verificar a conexão dos dispositivos e o funcionamento das restrições da rede de convidados.

| Teste                        | O que permite verificar                                                       |
| ---------------------------- | ----------------------------------------------------------------------------- |
| **Conexão wireless**         | Se os equipamentos conseguem se conectar às redes configuradas.               |
| **DHCP**                     | Se os dispositivos recebem endereços IPv4 automaticamente.                    |
| **Acesso à rede externa**    | Se os equipamentos conseguem acessar o site de teste do ambiente simulado.    |
| **Ping antes do isolamento** | Se existe comunicação entre dispositivos das redes principal e de convidados. |
| **Ping após o isolamento**   | Se a restrição impede a comunicação dos convidados com a rede interna.        |

**Observação:** os testes fazem parte do procedimento do laboratório. Como não foram apresentados resultados individuais, não é possível confirmar o sucesso de todas as verificações apenas pela descrição da atividade.

---

## Onde esse conhecimento pode ser aplicado?

**Cenário fictício: rede wireless para funcionários e visitantes**

Imagine uma pequena empresa que recebe clientes e fornecedores diariamente.

Os funcionários utilizam notebooks e dispositivos conectados à rede interna, enquanto os visitantes precisam de acesso à Internet.

Para evitar que pessoas externas tenham acesso direto aos equipamentos da empresa, o profissional de TI configura duas redes:

* **HomeNet:** utilizada pelos funcionários e dispositivos internos.
* **GuestNet:** destinada aos visitantes, com senha própria e acesso restrito à rede local.

Assim, os visitantes podem utilizar a Internet sem precisar se conectar à mesma rede dos funcionários.

**Resultado esperado:** oferecer acesso wireless aos visitantes e reduzir a exposição dos dispositivos internos.

**O que esse cenário ensina:** criar uma rede de convidados é uma medida importante de segurança, mas sua proteção depende da configuração correta do isolamento e de outros controles de acesso.

---

## Principais aprendizados

Com este laboratório, pude praticar configurações importantes para proteger redes wireless e controlar a conexão de diferentes dispositivos.

* **Segurança administrativa:** alteração de senhas padrão e desativação de acessos remotos desnecessários.
* **Proteção wireless:** utilização de WPA2 Personal e AES.
* **Separação de redes:** configuração de acessos diferentes para usuários internos e convidados.
* **DHCP:** atribuição automática de endereços IPv4.
* **Conectividade:** utilização de testes para investigar problemas de comunicação.
* **Dispositivos IoT:** conexão de equipamentos inteligentes à rede principal.

**O principal aprendizado foi entender como configurações simples de segurança ajudam a proteger uma rede, organizar o acesso dos dispositivos e reduzir riscos de acesso indevido.**

Esses conhecimentos podem ser aplicados em atividades de **Suporte de TI, Redes e Cybersecurity**.

---

## Entendendo os termos técnicos

| Termo                        | Explicação simples                                                             |
| ---------------------------- | ------------------------------------------------------------------------------ |
| **Roteador**                 | Equipamento que conecta dispositivos a outras redes, como a Internet.          |
| **Wireless**                 | Conexão de rede sem a utilização de cabos.                                     |
| **SSID**                     | Nome da rede que aparece na lista de conexões disponíveis.                     |
| **WPA2 Personal**            | Proteção que exige uma senha para conectar à rede wireless.                    |
| **AES**                      | Tecnologia utilizada para criptografar e proteger as informações transmitidas. |
| **DHCP**                     | Serviço que atribui endereços IP automaticamente aos dispositivos.             |
| **Gateway**                  | Endereço utilizado para acessar outras redes.                                  |
| **Ping**                     | Comando utilizado para verificar se outro dispositivo responde pela rede.      |
| **IoT**                      | Dispositivos inteligentes conectados à rede, como câmeras e sensores.          |
| **Isolamento de convidados** | Restrição que impede visitantes de acessar diretamente a rede principal.       |

---

## Sobre o laboratório

Atividade educacional da **Cisco Networking Academy (NetAcad)**, desenvolvida no Cisco Packet Tracer para estudar a configuração e a proteção de redes wireless.

O laboratório faz parte do meu portfólio de estudos em **Redes de Computadores, Suporte de TI e Cybersecurity**.
