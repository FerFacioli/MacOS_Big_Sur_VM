

# Relatório de Grupo: Análise do Sistema Operacional macOS Big Sur

## Arquitetura, Instalação e Aplicações na Computação Moderna

![Logo]([[https://sdmntprsouthcentralus.oaiusercontent.com/files/00000000-ae94-61f7-8c15-dfe876926cc3/raw?se=2025-05-21T02%3A22%3A58Z&sp=r&sv=2024-08-04&sr=b&scid=ae1f8bf5-bafc-55fe-898d-f3765a2f1dad&skoid=5cab1ff4-c20d-41dc-babb-df0c2cc21dd4&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2025-05-20T22%3A54%3A15Z&ske=2025-05-21T22%3A54%3A15Z&sks=b&skv=2024-08-04&sig=JNIFuc2h42V53HPHfLTkW2hgluSA7QO/Oq%2BFmQ0JhJ8%3D](https://sdmntprsouthcentralus.oaiusercontent.com/files/00000000-ae94-61f7-8c15-dfe876926cc3/raw?se=2025-05-21T19%3A40%3A07Z&sp=r&sv=2024-08-04&sr=b&scid=32508217-b157-5acc-a4b8-ab7edae896c3&skoid=732f244e-db13-47c3-bcc7-7ee02a9397bc&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2025-05-21T13%3A52%3A40Z&ske=2025-05-22T13%3A52%3A40Z&sks=b&skv=2024-08-04&sig=L0IK1isYubhXPl9u/4GI96CC%2B2CC9p96t0dPn/chkuM%3D)](https://sdmntprsouthcentralus.oaiusercontent.com/files/00000000-ae94-61f7-8c15-dfe876926cc3/raw?se=2025-05-21T19%3A40%3A07Z&sp=r&sv=2024-08-04&sr=b&scid=32508217-b157-5acc-a4b8-ab7edae896c3&skoid=732f244e-db13-47c3-bcc7-7ee02a9397bc&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2025-05-21T13%3A52%3A40Z&ske=2025-05-22T13%3A52%3A40Z&sks=b&skv=2024-08-04&sig=L0IK1isYubhXPl9u/4GI96CC%2B2CC9p96t0dPn/chkuM%3D))
https://www.youtube.com/watch?v=SoR8OCQj-zg&t=344s

---

### Resumo

Apesar do crescimento do uso de sistemas baseados em Unix, como o macOS, observa-se que ainda há pouco conhecimento entre estudantes da área de tecnologia sobre sua arquitetura, funcionamento e diferenciais em relação a outros sistemas operacionais. Este trabalho visa preencher essa lacuna ao abordar aspectos técnicos e práticos do macOS Big Sur, incluindo a instalação do sistema operacional em ambiente de teste.

**Palavras-chave:** macOS Big Sur, sistema operacional, Unix, arquitetura, instalação.

---

## 1. Introdução

Os sistemas operacionais desempenham papel fundamental na interação entre usuários e hardware. Em virtude da diversidade de plataformas disponíveis, o conhecimento sobre diferentes sistemas é essencial para profissionais da área de tecnologia. O macOS, desenvolvido pela Apple Inc., é um sistema baseado em Unix, amplamente utilizado em computadores da linha Mac. Esta pesquisa tem como foco o macOS Big Sur, lançado em 2020, que marcou uma transição relevante na interface gráfica e no suporte a novos processadores da Apple. O objetivo deste estudo é analisar o funcionamento do sistema, destacar suas principais características e realizar uma instalação prática, registrada em vídeo, para ilustrar seu comportamento em ambiente real.

---

## 2. Revisão da Literatura

Diversos autores e fontes documentam os aspectos técnicos do macOS. Segundo a Apple, o Big Sur é o primeiro sistema operacional projetado para funcionar de forma nativa com os processadores Apple Silicon, como o M1. O sistema traz melhorias significativas na interface de usuário, privacidade, segurança e desempenho. Pesquisas acadêmicas destacam sua base Unix (BSD) como um diferencial em estabilidade e segurança, além da arquitetura híbrida que permite executar tanto aplicações legadas (Intel) quanto nativas (ARM). Em comparação a sistemas como Windows e Linux, o macOS apresenta integração mais rígida com o hardware, proporcionando maior otimização, mas menor flexibilidade.

---

## 3. Metodologia

A abordagem metodológica deste trabalho foi exploratória e prática. A primeira fase consistiu em uma revisão bibliográfica em sites oficiais, artigos acadêmicos e documentações técnicas. Na segunda fase, realizou-se a instalação prática do macOS Big Sur em uma máquina virtual e, posteriormente, em um computador Apple, com todo o processo documentado em vídeo. Essa etapa permitiu avaliar a interface, desempenho e facilidade de uso do sistema, incluindo testes com softwares nativos e de terceiros.

---

## 4. Procedimentos para Instalação do macOS Big Sur via VirtualBox

### 4.1. Introdução

A virtualização utilizando o VirtualBox permite executar sistemas operacionais dentro de ambientes simulados, sendo útil para testes, estudos e desenvolvimento. Neste relatório, será demonstrado o processo de instalação do macOS em uma máquina virtual.

#### **Componentes necessários:**
- VirtualBox
- Imagem do macOS no formato `.iso`
- VirtualBox Extension Pack

A instalação do Extension Pack deve ser realizada após a instalação do VirtualBox, acessando o menu "Ferramentas".

### 4.2. Criação da Máquina Virtual

1. Clique em “Novo” e nomeie a máquina como "macOS" (facilita comandos posteriores).
2. Selecione o tipo “Mac OS X” e a versão “Mac OS X (64-bit)”.
3. Configure entre 1 a 2 processadores, pelo menos 4 GB de memória RAM e espaço em disco superior a 50 GB (o sistema ocupa cerca de 20 GB).
4. Utilize o tipo de disco rígido virtual VDI (VirtualBox Disk Image).
5. Configure o display para 128 MB e o controlador USB para USB 3.0.

### 4.3. Configuração via Prompt de Comando

Feche o VirtualBox antes de prosseguir. No Prompt de Comando (CMD), aplique comandos para garantir compatibilidade entre o VirtualBox e o macOS, simulando características de hardware Apple.

#### **Para processadores AMD:**
```sh
cd "C:\Program Files\Oracle\VirtualBox\"
VBoxManage modifyvm “macos” --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff
VBoxManage setextradata "macos" VBoxInternal/Devices/efi/0/Config/DmiSystemProduct “MacBookPro15,1”
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Mac-551B86E5744E2388"
VBoxManage setextradata "macos" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"
VBoxManage setextradata "macos" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1
```

#### **Para processadores Intel:**
```sh
cd "C:\Program Files\Oracle\VirtualBox\"
VBoxManage.exe modifyvm "macos" --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff 
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMac11,3" 
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0" 
VBoxManage setextradata "macos" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Iloveapple" 
VBoxManage setextradata "macos" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc" 
VBoxManage setextradata "macos" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1
VBoxManage modifyvm "macos" --cpu-profile "Intel Core i7-6700K"
```

### 4.4. Instalação do macOS

Após executar os comandos, abra novamente o VirtualBox e inicie a máquina virtual. Siga os passos:

1. Selecione o idioma desejado.
2. Acesse **Disk Utility** (Utilitário de Disco).
3. Localize o disco virtual de 50 GB, selecione e clique em **Erase** (Apagar); utilize o nome "macOS", formato APFS, esquema GUID Partition Map.
4. Retorne ao menu principal e selecione **Install macOS Big Sur**.
5. Clique em **Continuar** e aguarde a instalação.
6. Após a reinicialização, siga as etapas de configuração inicial:
    - Selecione país/região.
    - Ajuste configurações de teclado, acessibilidade e voz.
    - Na Migração de Dados, escolha “Not Now” (caso não vá transferir dados).
    - Faça login com um ID Apple ou pule.
    - Aceite os termos de uso.
    - Crie um usuário local com nome e senha.
    - Complete as configurações até a área de trabalho.

Durante essa etapa, é possível ativar/desativar funções como Serviços de Localização, Siri e opções de privacidade, ajustáveis posteriormente. Recomenda-se manter o layout de teclado como ANSI para maior compatibilidade.

---

## 5. Resultados

A instalação foi concluída com sucesso, demonstrando a viabilidade do teste do macOS Big Sur em ambiente controlado. O vídeo produzido ilustra o processo detalhado, desde a preparação do disco até a configuração inicial do sistema. Foram identificadas vantagens como fluidez da interface, integração com o ecossistema Apple, segurança aprimorada e excelente gerenciamento de energia. Como limitação, destaca-se a baixa compatibilidade com hardware não-Apple, dificultando a virtualização em sistemas convencionais. Espera-se que os resultados promovam maior entendimento entre estudantes e incentivem a exploração de ambientes além do Windows.

---

## 6. Conclusão

O estudo do macOS Big Sur permitiu compreender a estrutura de um sistema Unix moderno voltado ao uso comercial e profissional. A instalação prática e a análise funcional revelaram um sistema robusto, seguro e com design sofisticado, embora restrito à plataforma Apple. No contexto acadêmico, conhecer o macOS amplia o repertório técnico dos alunos, prepara para ambientes multiplataforma e estimula a busca por soluções mais eficientes e seguras. O vídeo produzido serve como material complementar para estudantes e demais interessados em operar ou instalar o sistema.

---

## 7. Referências

- APPLE INC. “macOS Big Sur – Technical Overview”. Disponível em: https://developer.apple.com/macos/
- TANENBAUM, A. S. Modern Operating Systems. Pearson, 2015.
- SILBERSCHATZ, A.; GALVIN, P. B.; GAGNE, G. Operating System Concepts. Wiley, 2018.
- MACH Kernel Development – GNU Project. Disponível em: https://www.gnu.org/software/hurd/hurd.html
- CARVALHO, R. “Comparativo entre sistemas operacionais: Windows, Linux e macOS”. Revista InfoTech, 2021.

---
