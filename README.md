# Servidor Minecraft Forge 1.20.1 no GitHub Actions

Este repositório contém a estrutura completa para rodar um servidor de Minecraft (versão 1.20.1 com Forge) de forma gratuita utilizando o GitHub Actions.

## 🚀 Funcionalidades

- **Minecraft 1.20.1 com Forge**: Suporte completo a mods.
- **Hospedagem Gratuita**: Utiliza os runners do GitHub Actions (até 6 horas por execução).
- **IP Dinâmico por E-mail**: O IP de conexão é gerado via túnel (Pinggy) e enviado automaticamente para o seu e-mail (`pabloluizgz@gmail.com`).
- **Suporte a Mods**: Basta adicionar os arquivos `.jar` na pasta `mods/` do repositório.
- **Auto-Save**: O mundo é salvo automaticamente no repositório antes do servidor ser desligado.

## ⚙️ Como Configurar

### 1. Preparar o Repositório
Faça o upload de todos os arquivos desta estrutura para o seu repositório no GitHub: `https://github.com/PabloVTB/Servidor`

### 2. Configurar os Segredos (Secrets) para o E-mail
Para que o GitHub Actions consiga enviar o e-mail com o IP do servidor, você precisa configurar as credenciais do seu e-mail no repositório.

1. Vá até a aba **Settings** (Configurações) do seu repositório no GitHub.
2. No menu lateral esquerdo, clique em **Secrets and variables** > **Actions**.
3. Clique no botão verde **New repository secret**.
4. Crie os seguintes segredos:
   - **Nome**: `EMAIL_USERNAME`
     - **Valor**: Seu endereço de e-mail do Gmail (ex: `seu-email@gmail.com`).
   - **Nome**: `EMAIL_PASSWORD`
     - **Valor**: Uma **Senha de Aplicativo** gerada na sua conta Google. *(Não use sua senha normal! Vá nas configurações de segurança da sua Conta Google, ative a Verificação em Duas Etapas e crie uma "Senha de app" para usar aqui).*

### 3. Configurar Permissões do GitHub Actions
Para que o servidor consiga salvar o mundo automaticamente no repositório:
1. Vá em **Settings** > **Actions** > **General**.
2. Role a página até a seção **Workflow permissions**.
3. Selecione a opção **Read and write permissions**.
4. Clique em **Save**.

## 🎮 Como Adicionar Mods

1. Navegue até a pasta `mods/` no seu repositório.
2. Faça o upload dos arquivos `.jar` dos mods que deseja utilizar (certifique-se de que são compatíveis com a versão 1.20.1 do Forge).
3. O GitHub Actions irá copiar automaticamente esses mods para o servidor na próxima vez que ele iniciar.

## 🔄 Como Iniciar o Servidor

O servidor iniciará automaticamente de duas formas:
1. **Manualmente**: Vá na aba **Actions**, selecione o workflow "Minecraft Forge 1.20.1 Server" e clique em **Run workflow**.
2. **Agendado**: O servidor está configurado para reiniciar automaticamente a cada 5 horas para contornar o limite de 6 horas do GitHub Actions.

## ⚠️ Limitações Importantes

- **Tempo de Execução**: O GitHub Actions tem um limite máximo de 6 horas por job. O servidor foi configurado para rodar por 5 horas e 30 minutos, salvar o mundo e desligar.
- **IP Dinâmico**: O IP mudará a cada reinicialização. Você sempre receberá o novo IP no seu e-mail.
- **Performance**: Os runners gratuitos do GitHub Actions possuem 2 vCPUs e 7GB de RAM. É suficiente para jogar com alguns amigos e alguns mods, mas pode apresentar lag (TPS baixo) se houver muitos jogadores ou mods muito pesados.
